# slip9


Q.1 Design simple HR Application using Spring Framework 
Q 2. Write a python program to implement Linear SVM.
Q. 3 Create a node.js file that Select all records from the "customers" table, and display the
result object on console.


Q.1 Design simple HR Application using Spring Framework

:public interface UserLister {
    List<User> getUsers();
}


public class UserListerDB implements UserLister {
    public List<User> getUsers() {
        // DB access code here
    }
}


public class SomeView {
    private UserLister userLister;

    public void render() {
        List<User> users = userLister.getUsers();
        view.render(users);
    }
}


UserLister userLister = new UserListerDB();


UserLister userLister = new UserListerCommaSeparatedFile();


<bean id="userLister" class="UserListerDB" />

<bean class="SomeView">
    <property name="userLister" ref="userLister" />
</bean>


@Inject
private UserLister userLister;


List<User> users = userLister.getUsers();  // This will actually work
                                           // without adding any line of code


Q 2. Write a python program to implement Linear SVM.
:
from sklearn import svm

# Load the training data
X = [[0, 0], [1, 1]]
y = [0, 1]

# Create the SVM model
model = svm.SVC(kernel='linear')

# Fit the model to the training data
model.fit(X, y)

# Make predictions on new data
x_new = [[2, 2]]
predictions = model.predict(x_new)
print(predictions)  # Output: [1]


Q. 3 Create a node.js file that Select all records from the "customers" table, and display the
result object on console. 

:
var mysql = require('mysql');
var con = mysql.createConnection({
host: "localhost",
user: "yourusername",
password: "yourpassword",
database: "mydb"
});
con.connect(function(err) {
if (err) throw err;
con.query("SELECT * FROM customers", function (err, result, fields)
{
 if (err) throw err;
 console.log(result);
});
});

