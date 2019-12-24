# globPDFS
glob some PDFs and process using NLTK and perhaps pandas
#First create a Jupyter Notebook

#Then get the PDFS using glob
            import PyPDF2
            import glob

            pdf_dir = "/home/scott/projects/RedTideResearch/dataHarvests"

            pdf_files = glob.glob("%s/*.pdf" % pdf_dir)
            for file in pdf_files:
                print(file)
                open(file, 'rb')
                print(PyPDF2.PdfFileReader(file))

#Merge them into one big file

                # importing required modules 
                import PyPDF2 
                
                def PDFmerge(pdfs, output):  
                    # creating pdf file merger object 
                    pdfMerger = PyPDF2.PdfFileMerger() 
                    
                    # appending pdfs one by one 
                    for pdf in pdfs: 
                        with open(pdf, 'rb') as f: 
                            pdfMerger.append(f) 
                        
                    # writing combined pdf to output pdf file 
                    with open(output, 'wb') as f: 
                        pdfMerger.write(f) 
                
                def main(): 
                    # pdf files to merge 
                    pdfs = ['example.pdf', 'rotated_example.pdf'] 
                    
                    # output pdf file name 
                    output  = 'combined_example.pdf'
                    
                    # calling pdf merge function 
                    PDFmerge(pdfs = pdfs, output = output) 
                
                if __name__ == "__main__": 
                    # calling the main function 
                    main() 

#Extract the text from the merged documents

                1. Extracting text from PDF file

                # importing required modules 
                import PyPDF2 
                
                # creating a pdf file object 
                pdfFileObj = open('example.pdf', 'rb') 
                
                # creating a pdf reader object 
                pdfReader = PyPDF2.PdfFileReader(pdfFileObj) 
                
                # printing number of pages in pdf file 
                print(pdfReader.numPages) 
                
                # creating a page object 
                pageObj = pdfReader.getPage(0) 
                
                # extracting text from page 
                print(pageObj.extractText()) 
                
                # closing the pdf file object 
                pdfFileObj.close() 


#Use NLTK to do tokenizing


#Then use pandas to visualize the results