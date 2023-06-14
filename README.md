package com.sun.content.server.operator.security.adaptor; 
import com.sun.content.server.service.security.User; 
import java.util.Date; 
import java.util.Hashtable; 
 
public class SampleUserImpl implements User 
{ 
 
    private Hashtable fInfo; 
 
    public SampleUserImpl() { 
 
        fInfo = new Hashtable(); 
 
        setLoginId("guest"); 
        setFirstName("guest"); 
        setLastName("guest"); 
        setPassword ("guest"); 
        setCreateDate(new Date()); 
        setActivateDate(new Date()); 
        fInfo.put("enabled", String.valueOf(true)); 
        setMiddleName("guest"); 
        setEmail("guest@email.com"); 
        setUniqueDeviceId("1231231233"); 
    } 
 
    public SampleUserImpl(String uid, String pwd, String fname, String lname,String mname,String gender, 
       String street1, String street2,String city, String state,String postalcode, 
       String country,String email,String phone,Date actdate,Date deactdate, 
       String salutation, boolean enabled, String uniqueDeviceId, boolean isprepay) { 
 
        fInfo = new Hashtable(); 
 
        setLoginId(uid); 
        setPassword(pwd); 
        setFirstName(fname); 
        setLastName(lname); 
        setMiddleName(mname); 
        setGender(gender); 
        setStreet1(street1); 
        setStreet2(street2); 
        setCity(city); 
        setState(state); 
        setPostalCode(postalcode); 
        setCountry(country); 
        setEmail(email); 
        setPhone(phone); 
        setFixedPhone(phone); 
         
        // It is safe to check the activation date and use current date if null 
        if ( actdate == null ) { 
            setCreateDate(new Date()); 
            setActivateDate(new Date()); 
        } 
        else { 
            setCreateDate(actdate); 
            setActivateDate(actdate); 
        } 
         
	   	setDeActivateDate(deactdate); 
        setSalutation(salutation); 
        setIsEnabled(enabled); 
        setUniqueDeviceId(uniqueDeviceId); 
        setIsPrepay(isprepay); 
    } 
 
