---
title: 'Vorgehensweise: Festlegen der JPEG-Komprimierungsebene'
description: Erfahren Sie, wie Sie die Qualität eines JPEG-Bilds anpassen, indem Sie die Komprimierungs Ebene in Windows Forms ändern.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], changing encoder parameters
- JPEG images [Windows Forms], setting quality level
ms.assetid: 4b9a74e3-9504-43c1-9f28-ace651d0772e
ms.openlocfilehash: 1f6a96e8a05fff40eb08da0ce318faa86a06cc3a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618713"
---
# <a name="how-to-set-jpeg-compression-level"></a><span data-ttu-id="153d8-103">Vorgehensweise: Festlegen der JPEG-Komprimierungsebene</span><span class="sxs-lookup"><span data-stu-id="153d8-103">How to: Set JPEG Compression Level</span></span>
<span data-ttu-id="153d8-104">Möglicherweise möchten Sie die Parameter eines Bilds ändern, wenn Sie das Bild auf einem Datenträger speichern, um dadurch die Dateigröße zu minimieren oder die Qualität zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="153d8-104">You may want to modify the parameters of an image when you save the image to disk to minimize the file size or improve its quality.</span></span> <span data-ttu-id="153d8-105">Sie können die Qualität eines JPEG-Bilds anpassen, indem Sie seine Komprimierungsebene ändern.</span><span class="sxs-lookup"><span data-stu-id="153d8-105">You can adjust the quality of a JPEG image by modifying its compression level.</span></span> <span data-ttu-id="153d8-106">Um die Komprimierungs Ebene beim Speichern eines JPEG-Bilds anzugeben, müssen Sie ein <xref:System.Drawing.Imaging.EncoderParameters> -Objekt erstellen und es an die- <xref:System.Drawing.Image.Save%2A> Methode der- <xref:System.Drawing.Image> Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="153d8-106">To specify the compression level when you save a JPEG image, you must create an <xref:System.Drawing.Imaging.EncoderParameters> object and pass it to the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="153d8-107">Initialisieren Sie das- <xref:System.Drawing.Imaging.EncoderParameters> Objekt, sodass es über ein Array verfügt, das aus einem Array besteht <xref:System.Drawing.Imaging.EncoderParameter> .</span><span class="sxs-lookup"><span data-stu-id="153d8-107">Initialize the <xref:System.Drawing.Imaging.EncoderParameters> object so that it has an array that consists of one <xref:System.Drawing.Imaging.EncoderParameter>.</span></span> <span data-ttu-id="153d8-108">Wenn Sie das Erstellen <xref:System.Drawing.Imaging.EncoderParameter> , geben Sie den <xref:System.Drawing.Imaging.Encoder.Quality> Encoder und die gewünschte Komprimierungs Ebene an.</span><span class="sxs-lookup"><span data-stu-id="153d8-108">When you create the <xref:System.Drawing.Imaging.EncoderParameter>, specify the <xref:System.Drawing.Imaging.Encoder.Quality> encoder, and the desired compression level.</span></span>  
  
## <a name="example"></a><span data-ttu-id="153d8-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="153d8-109">Example</span></span>  
 <span data-ttu-id="153d8-110">Im folgenden Beispielcode wird ein <xref:System.Drawing.Imaging.EncoderParameter> -Objekt erstellt und drei JPEG-Bilder gespeichert.</span><span class="sxs-lookup"><span data-stu-id="153d8-110">The following example code creates an <xref:System.Drawing.Imaging.EncoderParameter> object and saves three JPEG images.</span></span> <span data-ttu-id="153d8-111">Jedes JPEG-Bild wird mit einer anderen Qualitätsstufe gespeichert, indem der `long` an den Konstruktor übergeben Wert geändert wird <xref:System.Drawing.Imaging.EncoderParameter> .</span><span class="sxs-lookup"><span data-stu-id="153d8-111">Each JPEG image is saved with a different quality level, by modifying the `long` value passed to the <xref:System.Drawing.Imaging.EncoderParameter> constructor.</span></span> <span data-ttu-id="153d8-112">Die Qualitätsstufe 0 steht für die höchste, die Qualitätsstufe 100 für die niedrigste Komprimierung.</span><span class="sxs-lookup"><span data-stu-id="153d8-112">A quality level of 0 corresponds to the greatest compression, and a quality level of 100 corresponds to the least compression.</span></span>  
  
```csharp  
private void VaryQualityLevel()  
    {  
        // Get a bitmap. The using statement ensures objects  
        // are automatically disposed from memory after use.  
        using (Bitmap bmp1 = new Bitmap(@"C:\TestPhoto.jpg"))  
        {  
            ImageCodecInfo jpgEncoder = GetEncoder(ImageFormat.Jpeg);  
  
            // Create an Encoder object based on the GUID  
            // for the Quality parameter category.  
            System.Drawing.Imaging.Encoder myEncoder =  
                System.Drawing.Imaging.Encoder.Quality;  
  
            // Create an EncoderParameters object.  
            // An EncoderParameters object has an array of EncoderParameter  
            // objects. In this case, there is only one  
            // EncoderParameter object in the array.  
            EncoderParameters myEncoderParameters = new EncoderParameters(1);  
  
            EncoderParameter myEncoderParameter = new EncoderParameter(myEncoder, 50L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"c:\TestPhotoQualityFifty.jpg", jpgEncoder, myEncoderParameters);  
  
            myEncoderParameter = new EncoderParameter(myEncoder, 100L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"C:\TestPhotoQualityHundred.jpg", jpgEncoder, myEncoderParameters);  
  
            // Save the bitmap as a JPG file with zero quality level compression.  
            myEncoderParameter = new EncoderParameter(myEncoder, 0L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"C:\TestPhotoQualityZero.jpg", jpgEncoder, myEncoderParameters);  
        }  
    }  
```  
  
```vb  
Private Sub VaryQualityLevel()  
    ' Get a bitmap. The Using statement ensures objects  
    ' are automatically disposed from memory after use.  
    Using bmp1 As New Bitmap("C:\test\TestPhoto.jpg")  
        Dim jpgEncoder As ImageCodecInfo = GetEncoder(ImageFormat.Jpeg)  
  
        ' Create an Encoder object based on the GUID  
        ' for the Quality parameter category.  
        Dim myEncoder As System.Drawing.Imaging.Encoder = System.Drawing.Imaging.Encoder.Quality  
  
        ' Create an EncoderParameters object.  
        ' An EncoderParameters object has an array of EncoderParameter  
        ' objects. In this case, there is only one  
        ' EncoderParameter object in the array.  
        Dim myEncoderParameters As New EncoderParameters(1)  
  
        Dim myEncoderParameter As New EncoderParameter(myEncoder, 50L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("c:\test\TestPhotoQualityFifty.jpg", jpgEncoder, myEncoderParameters)  
  
        myEncoderParameter = New EncoderParameter(myEncoder, 100L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("C:\test\TestPhotoQualityHundred.jpg", jpgEncoder, myEncoderParameters)  
  
        ' Save the bitmap as a JPG file with zero quality level compression.  
        myEncoderParameter = New EncoderParameter(myEncoder, 0L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("C:\test\TestPhotoQualityZero.jpg", jpgEncoder, myEncoderParameters)  
    End Using  
End Sub  
```  
  
```csharp  
private ImageCodecInfo GetEncoder(ImageFormat format)  
{  
    ImageCodecInfo[] codecs = ImageCodecInfo.GetImageDecoders();  
    foreach (ImageCodecInfo codec in codecs)  
    {  
        if (codec.FormatID == format.Guid)  
        {  
            return codec;  
        }  
    }  
    return null;  
}  
```  
  
```vb  
Private Function GetEncoder(ByVal format As ImageFormat) As ImageCodecInfo  
  
    Dim codecs As ImageCodecInfo() = ImageCodecInfo.GetImageDecoders()  
    Dim codec As ImageCodecInfo  
    For Each codec In codecs  
        If codec.FormatID = format.Guid Then  
            Return codec  
        End If  
    Next codec  
    Return Nothing  
  
End Function  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="153d8-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="153d8-113">Compiling the Code</span></span>  
 <span data-ttu-id="153d8-114">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="153d8-114">This example requires:</span></span>  
  
- <span data-ttu-id="153d8-115">Eine Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="153d8-115">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="153d8-116">Ein <xref:System.Windows.Forms.PaintEventArgs> , bei dem es sich um einen Parameter von handelt <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="153d8-116">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
- <span data-ttu-id="153d8-117">Eine Bilddatei mit dem Namen `TestPhoto.jpg`, die unter **c:\\** gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="153d8-117">An image file that is named `TestPhoto.jpg` and located at **c:\\**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="153d8-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="153d8-118">See also</span></span>

- [<span data-ttu-id="153d8-119">Vorgehensweise: Ermitteln der von einem Encoder unterstützten Parameter</span><span class="sxs-lookup"><span data-stu-id="153d8-119">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)
- [<span data-ttu-id="153d8-120">Bitmaptypen</span><span class="sxs-lookup"><span data-stu-id="153d8-120">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="153d8-121">Verwenden von Bildencodern und -decodern in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="153d8-121">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
