# Exercise 5
class ClipList:
    def _init_(self, min=0, max=10):
        self.min = min
        self.max = max

    def _setitem_(self, key, value):
        return

    def _getitem_(self, key):
        return self.record[key]


my_list = ClipList()

my_list._setitem_(3, 10)
my_list._getitem_(1)
