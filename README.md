# DSA-SIDE-PROJECT
## Additional code for dsa mini project
### Function to extract and display a string from a file as requested by user
	case 2:
			printf("\n\nPlease Enter the Full Path of the file you want to open: \n");
			scanf("%s",&fname2);
			fptr2 = fopen(fname2, "r"); 
			    if (fptr2 == NULL) 
			    { 
				printf("Cannot open file %s \n", fname2); 
				exit(0); 
			    }
			printf("Enter name for searching:\n");
			scanf("%s",cmp);
			fgets(cmp, 50, stdin);
				err = Search_in_File(fname2);        
				if(err < 0)
                {
                    return err;
                }
                break;
### Function    
	int Search_in_File(char *fname) 
        {
        FILE *fp;
        int find_result = 0;
        char temp[100],*x,cmp[50];
		
	printf("Enter name for searching:\n");
	scanf("%s",cmp);
        if((fp = fopen(fname, "r")) == NULL)
          {	
            return(-1);
          }

        while(fgets(temp, 50, fp) != NULL)	// takes 50 chahrcters from file and stores it in temp and runs till end of file
          {
            	x=strstr(temp, cmp);
		if(x!= NULL) 		/*searches for string str in temp, if found it returns pointer to 									 *the first instance of the word found else it returns NULL 
              {			         */			
                printf("%s", temp);
                find_result++;
              }
          }

        if(find_result == 0) 
          {
            printf("\nSorry, couldn't find a match.\n");
          }
        if(fp) 
          {
            fclose(fp);
          }
        return(0);
      }
