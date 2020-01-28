# python_final_exam
# khu web/python class final exam
# 작성자 : gojiri
# 작성일 : 2020-01-28
# 언어 : python

class MyInteger():
    
    def __init__(self,user_value = 0):
        
        self.log = []
        
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
    
    def pressAdd(self,Add_value):
        
        if str(type(Add_value)) == "<class '__main__.MyInteger'>":
            self.value = self.value + Add_value.value
            self.log.append(("A",Add_value.value))
            return self.value
        
        elif type(Add_value) == float:
            self.value = self.value + int(Add_value)
            self.log.append(("A",int(Add_value)))
            return iself.value
        
        elif type(Add_value) == int:
            self.value = self.value + int(Add_value)
            self.log.append(("A",int(Add_value)))
            return self.value
        
        elif type(Add_value) == str:
            self.value = self.value + int(Add_value)
            self.log.append(("A",int(Add_value)))
            return self.value
    
    def pressSub(self,Sub_value):
        
        if str(type(Sub_value)) == "<class '__main__.MyInteger'>":
            self.value = self.value - Sub_value.value
            self.log.append(("S",Sub_value.value))
            return self.value
        
        elif type(Sub_value) == float:
            self.value = self.value - int(Sub_value)
            self.log.append(("S",int(Sub_value)))
            return iself.value
        
        elif type(Sub_value) == int:
            self.value = self.value - int(Sub_value)
            self.log.append(("S",int(Sub_value)))
            return self.value
        
        elif type(Sub_value) == str:
            self.value = self.value - int(Sub_value)
            self.log.append(("S",int(Sub_value)))
            return self.value
    
    def getCurrentVariable(self, oper_mode = None): #oper_mode : hex,oct,bin,None
        
        if oper_mode == "hex":
            return hex(self.value)
        
        elif oper_mode == "oct":
            return oct(self.value)
        
        elif oper_mode == "bin":
            return bin(self.value)
            
        elif oper_mode == None:
            return self.value
    
    def rollbackCurrentVariable(self,rollback_num):
        
        if rollback_num > len(self.log):
            
            for i in range(len(self.log)):
                if self.log[len(self.log)-1-i][0] == "S":
                    
                    self.value = self.value + self.log[len(self.log)-1-i][1]
                    self.log.pop()
                    
                if self.log[len(self.log)-1-i][0] == "A":
                    
                    self.value = self.value - self.log[len(self.log)-1-i][1]
                    self.log.pop()
        
        return self.value
                    
        else:
            
            for i in range(rollback_num):
                if self.log[len(self.log)-1-i][0] == "S":
                    
                    self.value = self.value + self.log[len(self.log)-1-i][1]
                    self.log.pop()
                    
                if self.log[len(self.log)-1-i][0] == "A":
                    
                    self.value = self.value - self.log[len(self.log)-1-i][1]
                    self.log.pop()
                    
        return self.value
        
    def resetCurrentVariable(self):
    
        self.log == []
        return self.value
