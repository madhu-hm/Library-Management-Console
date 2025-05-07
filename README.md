PROJECT : LIBRARY MANAGEMENT SYSTEM
TITLE : BOOK HIVE
TARGET AUDIENCE : Librarian
TYPE : B2B
TIMELINE : 2 weeks
BUDGET : 0
TOTAL MEMBERS : 1
FEATURES :
	Admin Functions:
		Registration
		Authentication(login/logout)
	Book Management:
		Add books
		Remove books
		Update books
		Search books
	User Management:
		Register new library members
		Update member information
		Remove members
		Track member history
	Borrowing details:
		Checkout books to members
		Process book returns
		Renew borrowed books
		Calculate and apply the fine
	Library management:
		Track total book collection
		Monitor available books and borrowed books
		Generate report on book status
	Search and reporting:
		Search books with the help of filters
		Generate borrowing reports
		Overdue book reports
		Popular books statistics
DATA MODEL:
	Admin-Class
		admin_id int
		name String
		email_id String
		password String
	Book-Class
		book_id String
		title String
		author String
		genre String
		total_copies int
		available_copies int
		isAvailable Boolean
	Member-Class
		member_id String
		name String
		emailid String
		phoneNo String/long
		address String
		DOB String
		history List<BorrowRecord>
	BorrowRecord-Class
		record_id String
		book Book
		member Member
		issue_date Date
		due_date Date
		return_date Date
		fine Double
	Library-Class
		library_id String
		name String
		incharge String
		address String
		phoneNo String/long
		emailid String
		capacity int
		total_books int
		available_books int
		opening_time Date/long
		wifi_password String
	FineCalculator-Class
		fine_per_day double
	ReportGenerator-Class
		borrowing_report List<BorrowRecord>
		overdue_report List<BorrowRecord>
		popular_books Map<Book,Integer>
	AuthenticationService-Class
		userName String
		password String
		login() Boolean
		logout() void
	SearchFilter-Class
		filterByTitle String
		filterByAuthor String
		filterByGenre String
		filterByAvailability Boolean


		
