# Employee-Management-System

class Employee:
    def __init__(self, name, age, salary):

        self.name = name
        self.age = age
        self.salary = salary

    def display_info(self):

               print("Name:", self.name, ", Age:", self.age, ", Salary:", self.salary)


class EmployeeSystem:
    def __init__(self):
        # employees list 
        self.employees = []

    def add_employee(self):
        # for add new employee
        name = input("Enter employee name: ")
        age = int(input("Enter employee age: "))
        salary = float(input("Enter employee salary: "))
        new_employee = Employee(name, age, salary)
        self.employees.append(new_employee)
        print("Employee added successfully.")

    def print_employees(self):
        # all employees
        if len(self.employees) == 0:
            print("No employees to display.")
        else:
            for emp in self.employees:
                emp.display_info()

    def delete_employee_by_age(self):
        # for delete employees by age
        age = int(input("Enter the age of employee to delete: "))
        found = False
        for emp in self.employees:
            if emp.age == age:
                self.employees.remove(emp)
                print("Employee deleted successfully.")
                found = True
                break
        if not found:
            print("No employee found with that age.")

    def update_salary_by_name(self):
        # for update the employee salary
        name = input("Enter the name of employee to update salary: ")
        found = False
        for emp in self.employees:
            if emp.name == name:
                new_salary = float(input("Enter the new salary: "))
                emp.salary = new_salary
                print("Salary updated successfully.")
                found = True
                break
        if not found:
            print("No employee found with that name.")


# main part for operating the system
def main():
    system = EmployeeSystem()

    while True:
        print("\nMenu:")
        print("1) Add new employee")
        print("2) Print all employees")
        print("3) Delete employee by age")
        print("4) Update salary by name")
        print("5) End program")

        choice = input("Enter your choice (1-5): ")

        if choice == "1":
            system.add_employee()
        elif choice == "2":
            system.print_employees()
        elif choice == "3":
            system.delete_employee_by_age()
        elif choice == "4":
            system.update_salary_by_name()
        elif choice == "5":
            print("Thank you for using Employee System. Goodbye!")

        else:
            print("Invalid choice, please try again.")


#  to run the program
if __name__ == "__main__":
    main()

