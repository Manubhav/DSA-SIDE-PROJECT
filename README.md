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
				err = Search_in_File(fname2, cmp);        
				if(err < 0)
                {
                    return err;
                }
                break;
### Function    
    int Search_in_File(char *fname, char *str) 
      {
        FILE *fp;
        int find_result = 0;
        char temp[100];

        if((fp = fopen(fname, "r")) == NULL) 
          {	
            return(-1);
          }

        while(fgets(temp, 50, fp) != NULL) 
          {
            if((strstr(temp, str)) != NULL) 
              {
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
