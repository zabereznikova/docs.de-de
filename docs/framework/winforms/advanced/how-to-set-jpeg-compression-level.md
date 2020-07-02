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
# <a name="how-to-set-jpeg-compression-level"></a>Vorgehensweise: Festlegen der JPEG-Komprimierungsebene
Möglicherweise möchten Sie die Parameter eines Bilds ändern, wenn Sie das Bild auf einem Datenträger speichern, um dadurch die Dateigröße zu minimieren oder die Qualität zu verbessern. Sie können die Qualität eines JPEG-Bilds anpassen, indem Sie seine Komprimierungsebene ändern. Um die Komprimierungs Ebene beim Speichern eines JPEG-Bilds anzugeben, müssen Sie ein <xref:System.Drawing.Imaging.EncoderParameters> -Objekt erstellen und es an die- <xref:System.Drawing.Image.Save%2A> Methode der- <xref:System.Drawing.Image> Klasse übergeben. Initialisieren Sie das- <xref:System.Drawing.Imaging.EncoderParameters> Objekt, sodass es über ein Array verfügt, das aus einem Array besteht <xref:System.Drawing.Imaging.EncoderParameter> . Wenn Sie das Erstellen <xref:System.Drawing.Imaging.EncoderParameter> , geben Sie den <xref:System.Drawing.Imaging.Encoder.Quality> Encoder und die gewünschte Komprimierungs Ebene an.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispielcode wird ein <xref:System.Drawing.Imaging.EncoderParameter> -Objekt erstellt und drei JPEG-Bilder gespeichert. Jedes JPEG-Bild wird mit einer anderen Qualitätsstufe gespeichert, indem der `long` an den Konstruktor übergeben Wert geändert wird <xref:System.Drawing.Imaging.EncoderParameter> . Die Qualitätsstufe 0 steht für die höchste, die Qualitätsstufe 100 für die niedrigste Komprimierung.  
  
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
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Eine Windows Forms-Anwendung  
  
- Ein <xref:System.Windows.Forms.PaintEventArgs> , bei dem es sich um einen Parameter von handelt <xref:System.Windows.Forms.PaintEventHandler> .  
  
- Eine Bilddatei mit dem Namen `TestPhoto.jpg`, die unter **c:\\** gespeichert ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Ermitteln der von einem Encoder unterstützten Parameter](how-to-determine-the-parameters-supported-by-an-encoder.md)
- [Bitmaptypen](types-of-bitmaps.md)
- [Verwenden von Bildencodern und -decodern in Managed GDI+](using-image-encoders-and-decoders-in-managed-gdi.md)
