## Model

For this lab I used Microsoft Co-Pilot.

## Using read.delim

When I initally attempted to knit the command from the source.md, I would get this erro:

"Error in `make.names()`:
! invalid multibyte string 1
Backtrace:
    ▆
 1. └─utils::read.delim(url)
 2.   └─utils::read.table(...)
 3.     └─base::make.names(col.names, unique = TRUE)

Quitting from pubh4201labtwo.Rmd:1-5 [setup]
Execution halted"

I copy and pasted this error into AI to ask what it meant. It told me that read.delim() is not working as it should because the dataset has column names that have special character. It told me instead to use a diffrent command

readtsv(url)

So I needed to install the readr package to use it. 

Now that I could knit it, I went to work on my transformation, which I decided the simplist route would be to find the average of some of the FPKM columns in the data.

So I assigned a expression variable called expr and assigned the columns to that variable. Then I took a function to take the average of the numbers in those columns and call it avg.expr.

But I ran into another error:

"processing file: pubh4201labtwo.Rmd


                                                                                                  
Error in `fpkm %>% select(contains("FPKM"))`:
! could not find function "%>%"

Quitting from pubh4201labtwo.Rmd:1-9 [setup]
Execution halted"

I copied and pasted it to AI and asked what it meant. It basically said that I need the dpylr library which I added to my notebook.

But then I got another erro:

"processing file: pubh4201labtwo.Rmd
                                                                                                  


Error in `rowMeans()`:
! 'x' must be numeric or complex
Backtrace:
    ▆
 1. └─base::rowMeans(expr, na.rm = TRUE)

Quitting from pubh4201labtwo.Rmd:1-10 [setup]
Execution halted"

The AI explained that the data I was trying to take the average of are not numeric but that they have letters and characters in them. So before commanding the average, all of the data in the collumns needs to be numeric. 

I could not find a code from my own research so I asked AI for a line to fix this and it gave me this:

expr <- expr %>%
  mutate(across(everything(), as.numeric))

It also told me to use the head() command to act as a preview to make sure the file is loading correctly. To make sure this wouldn't make another error, I first ran the code with the mutate() lines suggested and it worked, then I added this command.
