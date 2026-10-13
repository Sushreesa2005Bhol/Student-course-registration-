# Student-course-registration-

courses = {"Python", "Java", "C", "Web Development"}
registrations = {}

def register_course():
    name = input("Enter student name: ")
    course = input("Enter course name: ").title()

    if course not in courses:
        print("Course not available!")
        return

    if name not in registrations:
        registrations[name] = set()

    registrations[name].add(course)
    print("Registration successful!")

def drop_course():
    name = input("Enter student name: ")
    course = input("Enter course name: ").title()

    if name in registrations and course in registrations[name]:
        registrations[name].remove(course)
        print("Course dropped!")
    else:
        print("Registration not found!")

def show_registrations():
    for name, course_list in registrations.items():
        print(name, ":", sorted(course_list))

while True:
    print("\n1. Register Course")
    print("2. Drop Course")
    print("3. Show Registrations")
    print("4. Exit")

    choice = input("Enter choice: ")

    if choice == "1":
        register_course()
    elif choice == "2":
        drop_course()
    elif choice == "3":
        show_registrations()
    elif choice == "4":
        break
    else:
        print("Invalid choice!")
        
