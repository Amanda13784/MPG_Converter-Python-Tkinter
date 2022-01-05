# MPG_Converter-Python-Tkinter
#Python script using tkinter GUI. Calculates the MPG upon user data entry
import tkinter
#Create the class
class MilesGUI:
    def __init__(self):
        #Create the main window
        self.main_window = tkinter.Tk()
        
        #Create the frames
        self.gallons_frame = tkinter.Frame(self.main_window)
        self.miles_frame = tkinter.Frame(self.main_window)
        self.mpg_frame = tkinter.Frame(self.main_window)
        self.bottom_frame = tkinter.Frame(self.main_window)
        
        #Create the widgets for the gallons frame
        self.gallons_label = tkinter.Label(self.gallons_frame, text = 'Enter the number of gallons: ')
        self.gallons_entry = tkinter.Entry(self.gallons_frame, width = 10)
        
        #Pack the gallons frame widgets
        self.gallons_label.pack(side = 'left')
        self.gallons_entry.pack(side = 'left')
        
        #Create the widgets for the miles frame
        self.miles_label = tkinter.Label(self.miles_frame, text = 'Enter the number of miles: ')
        self.miles_entry = tkinter.Entry(self.miles_frame, width = 10)
        
        #Pack the miles frame widgets
        self.miles_label.pack(side = 'left')
        self.miles_entry.pack(side = 'left')
        
        #Create the widgets for the mpg frame
        self.result_label = tkinter.Label(self.mpg_frame, text = 'Miles Per Gallon: ')
        
        #Create a blank label
        self.mpg = tkinter.StringVar()
        self.mpg_label = tkinter.Label(self.mpg_frame, textvariable = self.mpg)
        
        #Pack the mpg frame widgets
        self.result_label.pack(side = 'left')
        self.mpg_label.pack(side = 'left')
        
        #Create the two buttons in the bottom frame
        self.mpg_button = tkinter.Button(self.bottom_frame, text = 'Calculate MPG',
                                         command = self.calculate_mpg)
        self.quit_button = tkinter.Button(self.bottom_frame, text = 'Quit',
                                          command = self.main_window.destroy)
        
        #Pack the widgets in the bottom frame
        self.mpg_button.pack(side = 'left')
        self.quit_button.pack(side = 'left')

        #Pack frames
        self.gallons_frame.pack()
        self.miles_frame.pack()
        self.mpg_frame.pack()
        self.bottom_frame.pack()

        #Enter the tkinter main loop
        tkinter.mainloop()
    #Define the show_info function

    def calculate_mpg(self):
        #Get the values entered
        self.gallons = float(self.gallons_entry.get())
        self.miles = float(self.miles_entry.get())
        #Calculate mpg
        self.miles_per_gallon = float(self.miles) / self.gallons
        #Update the mpg label
        self.mpg.set(self.miles_per_gallon)
    
        
        

#Create and instance of the MilesGUI        
mpg = MilesGUI()
