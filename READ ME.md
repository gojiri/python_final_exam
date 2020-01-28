# python_final_exam
# khu web/python class final exam
# 작성자 : gojiri
# 작성일 : 2020-01-28
# 언어 : python

class MyInteger():
    
    def __init__(self,user_value = 0):
        
        if type(user_value) == int:
            self.value = user_value
        
        elif type(user_value) == float:
            self.value = int(user_value)
        
        elif type(user_value) == str:
            self.value = int(user_value)
            
        elif str(type(user_value)) == "<class '__main__.MyInteger'>":
            self.value = user_value.value
        
        else:
            self.value = 0
        
 def __eq__(self, other):
        
        if str(type(other)) == "<class '__main__.MyInteger'>":
            return other.value == self.value
        
        elif type(other) == float:
            return int(other) == self.value
        
        elif type(other) == int:
            return int(other) == self.value
        
        elif type(other) == str:
            return int(other) == self.value
        
        else :
            return False
