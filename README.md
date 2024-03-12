package ja;
import java.util.Scanner;

public class Employee 
{
	static Scanner sc = new Scanner(System.in);
	int Eid, BS;
	String name;
	int MA = 300;
	float GS, HRA, DA;
	static int count = 0;
	
void get_data()
	{
		System.out.println("Enter Employee Id : ");
		Eid = sc.nextInt();
		System.out.println("Enter Name : ");
		name = sc.next();
		System.out.println("Enter Basic Salary : ");
		BS = sc.nextInt();
	}
		void cal()
	{
		HRA = (BS * 20) / 100;
		DA = (BS * 25) / 100;
		GS = BS + HRA + MA + DA;
	}
	
void Display()
	{
		System.out.println("Employee Id : " + Eid);
		System.out.println("Name : " + name);
		System.out.println("Basic Salary : " + BS);
		System.out.println("Gross Salary : " + GS);
	}
		static void query1(Employee ob[])
	{
		for (int i = 0; i < ob.length; i++)
		{
			if (ob[i].name.charAt(0) == 'N' || ob[i].name.charAt(0) == 'n')
			{
				System.out.println("Name of Employee whose name starts with N is " + ob[i].name + " and his gross salary is " + ob[i].GS);
			}
		}
	}
		static void query2(Employee ob[])
 {
		for (int i = 0; i < ob.length; i++)
		{
			if (ob[i].Eid == 107)
			{
				System.out.println("Gross Salary of Employee with Eid 107 : " + ob[i].GS);
			}
		}
	}
		static void query3(Employee ob[])
	{
		for (int i = 0; i < ob.length; i++)
		{
			if (ob[i].GS > 20000)
			{
				count = count + 1;
			}
		}
		System.out.println("Number of employees whose salary is more than 20000/- : " + count);
	}
	
public static void main(String ar[]) 
	{
		System.out.println("Enter the number of Employees");
		int n = sc.nextInt();
		Employee[] ob = new Employee[n];
		for (int i = 0; i < n; i++)
		{
			ob[i] = new Employee();
			ob[i].get_data();
			ob[i].cal();
		}
		for (int i = 0; i < n; i++)
		{
			ob[i].Display();
		}
			while (true)
		{
			System.out.println("Enter choice:");
			System.out.println("Enter 1 to display the name and gross salary of an employee whose name starts With 'n'");
			System.out.println("Enter 2 to display the Eid and gross salary whose Eid is equal to 107");
			System.out.println("Enter 3 to count the total number of employees whose salary more than 20000/-");
			int c = sc.nextInt();
			switch (c)
			{
				case 1:
					query1(ob);
					break;
				case 2:
					query2(ob);
					break;
				case 3:
					query3(ob);
					break;
			}
			System.out.println("want to continue?? y for yes and n for no");
			char ch = sc.next().charAt(0);
			if (ch == 'n') break;
		}
	}
}
