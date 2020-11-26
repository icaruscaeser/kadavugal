# kadavugal

This repo puts together a few tools to store the creds. It uses sqlite3 to store the data

## Requirements
- linux machine with bash
- sqlite3

## Initialization of database
    sqlite3 kadavugal.db ".read init_db.sql"

## Insert data into database
    /bin/bash insert_kadavu.sh

## Read data from database

The following command can be used to read all the creds data from the database

    sqlite3 kadavugal.db "select * from KadavugalDetails";

## Store .db file

You can export the .db file to any storage medium of your choice. But if you intend to store it in cloud or any other easily accessible medium, make sure to encrypt it with a key.

For example, it can be encrypted using AES algorithm.

    openssl enc -aes-256-cbc -pass pass:$passkey -p -in kadavugal.db -out kadavugal.enc

To decrypt the encrypted .db file

    openssl enc -aes-256-cbc -pass pass:$passkey -d -p -in kadavugal.enc -out kadavugal.db

>***$passkey*** in the above the commands should be replaced with the AES key.

