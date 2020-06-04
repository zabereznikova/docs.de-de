---
title: 'Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei'
ms.date: 07/20/2015
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
ms.openlocfilehash: 9608a48cb8b3fac1c71affa7a0a17e9789f94b18
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413153"
---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a><span data-ttu-id="46777-102">Gewusst wie: Schreiben von Objektdaten in eine XML-Datei (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46777-102">How to: Write Object Data to an XML File (Visual Basic)</span></span>
<span data-ttu-id="46777-103">Dieses Beispiel verwendet die <xref:System.Xml.Serialization.XmlSerializer>-Klasse, um das Objekt aus einer Klasse in eine XML-Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="46777-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46777-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46777-104">Example</span></span>  
  
```vb  
Public Module XMLWrite  
  
    Sub Main()  
        WriteXML()  
    End Sub  
  
    Public Class Book  
        Public Title As String  
    End Class  
  
    Public Sub WriteXML()  
        Dim overview As New Book  
        overview.Title = "Serialization Overview"  
        Dim writer As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
        Dim file As New System.IO.StreamWriter(  
            "c:\temp\SerializationOverview.xml")  
        writer.Serialize(file, overview)  
        file.Close()  
    End Sub  
End Module  
```  
  
## <a name="compile-the-code"></a><span data-ttu-id="46777-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="46777-105">Compile the code</span></span>  
 <span data-ttu-id="46777-106">Die Klasse muss über einen öffentlichen Konstruktor ohne Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="46777-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="46777-107">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="46777-107">Robust Programming</span></span>  
 <span data-ttu-id="46777-108">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="46777-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="46777-109">Die zu serialisierende Klasse verfügt nicht über einen öffentlichen, parameterlosen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="46777-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="46777-110">Die Datei ist bereits vorhanden und schreibgeschützt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="46777-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="46777-111">Der Pfad ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="46777-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="46777-112">Der Datenträger ist voll (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="46777-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="46777-113">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="46777-113">.NET Framework Security</span></span>  
 <span data-ttu-id="46777-114">Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="46777-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="46777-115">Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine `Create`-Berechtigung für den Ordner.</span><span class="sxs-lookup"><span data-stu-id="46777-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="46777-116">Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung für den `Write`-Zugriff, also eine geringere Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="46777-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="46777-117">Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die `Read`-Berechtigung für eine einzelne Datei erteilt werden (anstatt `Create`-Berechtigungen für den gesamten Ordner zu gewähren).</span><span class="sxs-lookup"><span data-stu-id="46777-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46777-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46777-118">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="46777-119">Gewusst wie: Lesen von Objektdaten aus einer XML-Datei (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46777-119">How to: Read Object Data from an XML File (Visual Basic)</span></span>](how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="46777-120">Serialisierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46777-120">Serialization (Visual Basic)</span></span>](index.md)
