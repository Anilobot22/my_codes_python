
class car:
    def open_the_door(self):
        print("Door Opened")
        self._start_the_engine()

    def _start_the_engine(self):         ### private _ ####
        print("Engine Running")
        self.__engage_the_gear()

    def __engage_the_gear(self):         ### protected __  ####
        print("Gear Engaged and Car Moving")

car1=car()
car1.open_the_door()
