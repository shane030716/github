# Import Java project from GitHub to Eclipse

Situation: My Java projects are stored in GitHub, switching to a new work station or computer. I need to import the projects into Eclipse.

Launch Eclipse.

Install the eGit plug-in if you haven't done so.

	Top Menu -> Help -> Eclipse Marketplace -> Search for eGit.

Open the Git perspective.

	If it's not there in the upper-right cornder, click Window in the top menu -> Perspective -> Open Perspective -> Other -> Git

Go to your GitHub repository (from a browser) and copy the repository URL.

On the top menu of the Git Repositories tab, click the icon "Clone a Git Repository and add the clone to this view", and paste the copied URL to the URI field.

Enter your GitHub username and password, and check "Store in Secure Store".

Click Next.

Select master branch (or your desired branch). Click Next.

Enter the directory for your local repository location (i.e. /Users/myusername/Developer/git/myprojectname). Click Finish.

Go back to the Java perspective.

Right click anywhere in the Navigator, click Import. (or File -> Import).

Select Git -> Projects from Git.

Select Existing local repository.

Select the local repository you just cloned from GitHub.

Select Import using the New Project wizard. Click Finish.

In the Select a wizard window. Select Java -> Java Project

Enter a Project name.

Uncheck the "Use default location", the browse to the directory of your local git repository. Click Next.

Click Finish. (Done)

