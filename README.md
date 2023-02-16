# Extract-text-from-document-in-bomi


import java.util.Properties;
import java.io.InputStream;
import com.boomi.execution.ExecutionUtil;

for( int i = 0; i < dataContext.getDataCount(); i++ ) {
    InputStream is = dataContext.getStream(i);
    Properties props = dataContext.getProperties(i);
    
    def iss = is.getText("UTF-8");
    def beg = iss.toString().indexOf("1000HDFRC");
    def op = iss.substring(beg+9,beg+21)
    
//    ExecutionUtil.getDynamicProcessProperty("DPP_Data");
    
    ExecutionUtil.setDynamicProcessProperty("DPP_Unique_Value", op, true);
    
    dataContext.storeStream(is, props);
}



![image](https://user-images.githubusercontent.com/97012694/219327076-16581127-155b-4544-8f71-f26ecb7afc81.png)
