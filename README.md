# QR-generator-
import qrcode

# Taking the URL as input you want to encode
url = input("Enter the url :")

# Creating a QR code instance
qr = qrcode.QRCode(
    version=1,  # controls the size of the QR code
    error_correction=qrcode.constants.ERROR_CORRECT_L,  # controls the errortolerance
    box_size=10,  # size of each box in the QR code
    border=4,  # thickness of the border
)

# Adding data to the QR code
qr.add_data(url)
qr.make(fit=True)

# Creating an image of the QR code
img = qr.make_image(fill="black", back_color="white")

# Saving the image
img.save("qrcode.png")
