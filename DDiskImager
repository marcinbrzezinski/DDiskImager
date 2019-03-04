#! /usr/bin/python3
# coding=utf-8
import os
import time
import hashlib
import logging


def hash(path):
    with open(path, "rb") as f:
        temp = f.read()
        sha256 = hashlib.sha256(temp).hexdigest()
        md5 = hashlib.md5(temp).hexdigest()
    return sha256, md5

def check_hash(input, output):
    if input == output:
        print("Sumy kontrolne są zgodne\n")
    else:
        print("!!! Sumy kontrolne się nie zgadzają !!!\n")


print("===============================")
print("        DDiskImager v1.0")
print("===============================\n")

print("Pamiętaj! Uruchom program z uprawnieniami root'a! (sudo ./main.py)\n")

# Pobranie ścieżki do pliku źródłowego
input_path = input("Podaj ścieżkę do pliku lub urządzenia źródłowego (np. /dev/sda1)\n")

# Obliczenie haszy dla źródła
input_sha256, input_md5 = hash(input_path)

# Podanie ścieżki do plliku docelowego
output_path = input("Podaj ścieżkę do pliku docelowego\n")
time_start = (time.time())
# Wykonanie obrazu
os.system("sudo dd if=" + input_path + " of=" + output_path + " status=progress")
time_end = time.time()

# Obliczenie haszy dla pliku wynikowego
output_sha256, output_md5 = hash(output_path)

print("==========================================================")
print("\nSHA265 dla źródła: " + input_sha256)
print("SHA265 dla wyniku: " + output_sha256)
check_hash(input_sha256, output_sha256)
print("==========================================================")
print("MD5 dla źródła: " + input_md5)
print("MD5 dla wyniku: " + output_md5)
check_hash(input_md5, output_md5)
print("==========================================================")




# Wyświetlenie czasu
print("Czas uruchomienia; " + time.strftime('%H:%M:%S', time.localtime(time_start)))
print("Czas zakończenia: " + time.strftime('%H:%M:%S', time.localtime(time_end)))
print("Operacja trwała: " + str(int(time_end - time_start)) + " sek. !")
