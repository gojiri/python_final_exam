# python_final_exam
# khu web/python class final exam
# 작성자 : gojiri
# 작성일 : 2020-01-28

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
        
