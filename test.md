Java--
cpu intesive- number of cores
io intensive- 

cache thread-->if they are idel for 60 sec. then kill that thread--



single thread--> create single thread and life cycle create new thread if in case it dies, and ensure that task run one after 
another


schedule
scheduleAtFixedRate
scheduleAtFixedDelay


parms-- corepoolsize,maxpoolsize,keepalivetime,workqueue,threadfactory,handler.

hadler(RejectionHandler)-->it's callback which ensure when task submitted and rejected and provide call back macanism


RejectionPolicy--
abortpolicy-->throw exc. RejectionHandlerException
discardpolicy-->submitted new task sliently discard abort thread
discardoldestpolicy-->addnew task and reject oldest one
callerunspolicy-->

Spring security---



Java
====================================
====================================
creat.
singleton---lazy-->double locking
factory
builder

beh.
temp
poroto
starategy

structural-
fligweight
structural
adapter
======================================

ExecutorService
LinkedList
BLockingQueue





package com.example.MongoTest;


import java.util.*;
import javax.mail.*;
import javax.mail.internet.*;

public class Main {

    private static String USER_NAME = "omj.akshaypanwar@gmail.com";  // GMail user name (just the part before "@gmail.com")
    private static String PASSWORD = "576923980700"; // GMail password
    private static String RECIPIENT = "omj.akshaypanwar@gmail.com";

    public static void main(String[] args) {
        String from = USER_NAME;
        String pass = PASSWORD;
        String[] to = { RECIPIENT }; // list of recipient email addresses
        String subject = "Java send mail example";
        String body = "Welcome to JavaMail!";

        sendFromGMail(from, pass, to, subject, body);
    }

    private static void sendFromGMail(String from, String pass, String[] to, String subject, String body) {
        Properties props = System.getProperties();
        String host = "smtp.gmail.com";
        props.put("mail.smtp.starttls.enable", "true");
        props.put("mail.smtp.host", host);
        props.put("mail.smtp.user", from);
        props.put("mail.smtp.password", pass);
        props.put("mail.smtp.port", "587");
        props.put("mail.smtp.auth", "true");

        Session session = Session.getDefaultInstance(props);
        MimeMessage message = new MimeMessage(session);

        try {
            message.setFrom(new InternetAddress(from));
            InternetAddress[] toAddress = new InternetAddress[to.length];

            // To get the array of addresses
            for( int i = 0; i < to.length; i++ ) {
                toAddress[i] = new InternetAddress(to[i]);
            }

            for( int i = 0; i < toAddress.length; i++) {
                message.addRecipient(Message.RecipientType.TO, toAddress[i]);
            }

            message.setSubject(subject);
            message.setText(body);
            Transport transport = session.getTransport("smtp");
            transport.connect(host, from, pass);
            transport.sendMessage(message, message.getAllRecipients());
            transport.close();
        }
        catch (AddressException ae) {
            ae.printStackTrace();
        }
        catch (MessagingException me) {
            me.printStackTrace();
        }
    }




}
