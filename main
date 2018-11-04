import csv
sum=0
average = 0
with open('students.csv', newline='') as studentsCsvFile:
    readStudentLine = csv.DictReader(studentsCsvFile)
    for studentRow in readStudentLine:
        #print("studentloop")
        print("Student Id: "+studentRow['id']+", name: "+studentRow['name'])

        with open('courses.csv', newline='') as coursesCsvFile: #open courses csv
            readCourseLine = csv.DictReader(coursesCsvFile)
            for courseRow in readCourseLine:
                #print("course loop")
                with open('tests.csv', newline='') as testsCsvFile: # open test csv
                    readTestLine = csv.DictReader(testsCsvFile)
                    for testRow in readTestLine:
                        #print("tests loop")

                        #print(courseRow['id'] +"\t" +testRow['course_id'])
                        if courseRow['id'] == testRow['course_id']:
                            with open('marks.csv', newline='') as marksCsvFile:
                                readMarksLine = csv.DictReader(marksCsvFile)
                                for marksRow in readMarksLine:
                                    if testRow['id'] == marksRow['test_id'] and studentRow['id'] == marksRow['student_id']:
                                        #print(marksRow['mark'], testRow['weight'])
                                        #print("marks iteration")
                                        markslist = marksRow['mark']
                                        testWeight = testRow['weight']
                                        percentage = float(markslist)*float(testWeight)/100
                                        sum = sum + percentage
                    #print(sum)
                    print("\tCourse: "+courseRow['name']+", Teacher: "+courseRow['teacher'])
                    print("\tFinal Grade: ", sum)
                    average += sum
                    sum = 0
        avg = average/3

        print("\tTotal Average:",avg)
        print()
        average = 0
