from PIL import Image

def encrypt_image(image_path, key):
    image = Image.open(image_path)
    encrypted_image = image.copy()
    width, height = image.size
    for y in range(height):
        for x in range(width):
            pixel = image.getpixel((x, y))
            encrypted_pixel = tuple((p + key) % 256 for p in pixel)
            encrypted_image.putpixel((x, y), encrypted_pixel)
    encrypted_image.save("encrypted_image.png")
    print("Image encrypted successfully!!")

def decrypt_image(image_path, key):
    encrypted_image = Image.open(image_path)
    decrypted_image = encrypted_image.copy()
    width, height = encrypted_image.size
    for y in range(height):
        for x in range(width):
            encrypted_pixel = encrypted_image.getpixel((x, y))
            decrypted_pixel = tuple((p - key) % 256 for p in encrypted_pixel)
            decrypted_image.putpixel((x, y), decrypted_pixel)
    decrypted_image.save("decrypted_image.png")
    print("Image decrypted successfully!!")

def main():
    print("1. Encrypt Image")
    print("2. Decrypt Image")
    choice = int(input("Enter your choice: "))
    if choice == 1:
        image_path = input("Enter path to the image to encrypt: ")
        key = int(input("Enter encryption key (an integer): "))
        encrypt_image(image_path, key)
    elif choice == 2:
        image_path = input("Enter path to the image to decrypt: ")
        key = int(input("Enter decryption key (an integer): "))
        decrypt_image(image_path, key)
    else:
        print("Invalid choice.")

if __name__ == "__main__":
    main()
