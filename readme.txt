This project aims to make a free(gnu) software for LINUX which can encrypt
decrypt files and folder.

/**** Project FF_NB *****/
@ author dZONE Date : 04-25-2012

basicxor.c v1.0 done: Uses simple xor operation on each byte
of data (04-25-2012)
aes2.c v1.0: done: Uses Openssl crypto API to implement AES256CBC
symetric cipher (05-01-2012)
cipher_file.c: v1.1: ??: Instead of creating a new encrypted and decrypted
files it will replace the original file, improvement on usability
cipher_helper.c: v1.0 : ?? : Contains helper functions

05-06-2012 :: File/Owner/Group Permission restore implemented.
Password Complexity Rules Implemented (MIn 2 digs,1 Caps, Min len 8).
05-10-2012 :: Keystore Iplemented: creat_keystore() creates a hidden file
in /home/user directory with 0600 permission set where these information
are stored in the given order:
		1. 32 Bytes: of PASSWORD HASH generated by using SHA256()
			with 32 Bytes salt(random)
		2. 32 Bytes: of SALT(password hash)
		3. 32 Bytes: of SALT(Session key)
		4. 32 Bytes: of V
		5. 48 Bytes: of E
		read_keystore() reads this data from Keystore.
05-11-2012 :: Now handles all file types (tested with pdf, jpg, docx,
		xlsx, pptx *decrypted files working fine on windows also*).
05-18-2012 :: The code now handles crypt operations on directories also.
(currently calls file module recurcivly need to implement threads for
efficienny).
05-20-2012 :: The code now handles the *REUSE* of existing keystore for crypt
operations.

