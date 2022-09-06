# Ritwik-Podder
Simlilearn Assessment
Project LockedMe.com
Code 1
package simplilearnFinalProject;
import java.util.Scanner;
import java.io.File;
import java.io.FileWriter;
public class LockedMe
{ 
    static final String projectFilesPath="C:\\Users\\User\\eclipse-workspace\\LockedMe.com\\src\\simplilearnFinalProject";
    // Denoting file location
	public static void displayMenu() 
	// Main driver method
	{
	System.out.println("*******************************************************************************");
	System.out.println(" \t\t WELCOME TO LOCKEDME.COM ");
	System.out.println("   This is secure application developed with Java using eclipse Workspace.\n Throught this application you can add files, delete files and search files.");
	System.out.println(" \t\t Developed by java developer Ritwik ");
	System.out.println("********************************************************************************");
	System.out.println("********************************************************************************\n");
	System.out.println("\t\t1.  Display all Files");
	System.out.println("\t\t2.  Add a new file");
              System.out.println("\t\t3.  Delete a file");
             System.out.println("\t\t4.  Exit from the application");
             //Display output
	}
	public static void getAllFiles()
	{
		File folder =new File(projectFilesPath);
		// Creating a file by creating object of File class
		File[] listofFiles = folder.listFiles();
		// Get all the names of the files present
		if(listofFiles.length>0)
			//method can be used on it to get its length
		{
			System.out.println("Files list is display below : \n");
			for(var l:listofFiles)
				// File available
			{
				System.out.println(l.getName());
			}
		}
		else
			{ 
				System.out.println("The folder is empty");
			}
	}
	public static void createFiles()
	{
	try
	
    // try-catch block to handle exceptions
	{
		Scanner obj =new Scanner(System.in);
		
		// Scanning input
		
		String fileName;
		System.out.println(" Enter the file name");
		//
		fileName=obj.nextLine();
		int linesCount;
		System.out.println(" Enter how many lines in the files: ");
		linesCount=Integer.parseInt(obj.nextLine());
		FileWriter fw = new FileWriter(projectFilesPath+"\\"+fileName);
		for(int i=1; i<=linesCount; i++)
		{
			System.out.println(" Enter file line : ");
			fw.write(obj.nextLine()+"\n");
		}
		System.out.println("File created successfully");
		fw.close();
	}
	catch (Exception e)
	//  Block of code to handle errors
	// when something went wrong
	{
		System.out.println("Something went wrong please start again");
	}
	}
	public static void deleteFile()
	{
		Scanner obj =new Scanner(System.in);
		// scanner input
		String fileName;
		System.out.println("Enter the file name: ");
		fileName=obj.nextLine();
		File f = new File(projectFilesPath+"\\"+fileName);
		if(f.exists())
		{
			f.delete();
			// delete function
			System.out.println("File deleted successfully");
		}
		else
		{
			System.out.println("file does not exist");
		}
	}

	public static void exitFile() {
		System.out.println(" Exiting the program ");
		System.out.println("******************************************************************************** \n");
		System.exit(0);
		// Exit program
		
	}}
Code 2
package simplilearnFinalProject;

import java.util.Scanner;
// Import the Scanner class

public class clientApp
{

	public static void main(String[] args)
	{
		Scanner obj = new Scanner(System.in);
		// Create a Scanner object
		int ch;
		do
		{
			LockedMe.displayMenu();
			// Inherited from another class
			
			System.out.println(" \t\tEnter your choice");
			
			ch=Integer.parseInt(obj.nextLine());
			
			//Read user input
			// It cannot take char as a parameter
			// Hence will throw an exception
			
			switch(ch)
			//Implementing switch case
			{
			case 1:LockedMe.getAllFiles();
			break;
			case 2:LockedMe.createFiles();
			break;
			case 3:LockedMe.deleteFile();
			break;
			case 4:LockedMe.exitFile();
			break;
			}
			
		}
		while(ch>0);
		obj.next();
		//read input till space character
		obj.close();
		//method of java Scanner class to close the scanner
		
	}

}

Output Window
*******************************************************************************
 		 WELCOME TO LOCKEDME.COM 
   This is secure application developed with Java using eclipse Workspace.
 Throught this application you can add files, delete files and search files.
 		 Developed by java developer Ritwik 
********************************************************************************
********************************************************************************

		1.  Display all Files
		2.  Add a new file
		3.  Delete a file
		4.  Exit from the application
 		Enter your choice
Git hub link
https://github.com/Ritwik72/Ritwik-Podder
