---
title: 'Gewusst wie: Lesen von Objektdaten aus einer XML-Datei'
ms.date: 07/20/2015
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
ms.openlocfilehash: c997af4729a24a6b5bd5b22d0153860cff3282d7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346425"
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="75816-102">Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75816-102">How to: Read Object Data from an XML File (Visual Basic)</span></span>
<span data-ttu-id="75816-103">In diesem Beispiel werden Objektdaten gelesen, die zuvor mithilfe der <xref:System.Xml.Serialization.XmlSerializer>-Klasse in eine XML-Datei geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="75816-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75816-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75816-104">Example</span></span>  
  
```vb  
Public Class Book  
    Public Title As String  
End Class  
  
Public Sub ReadXML()  
    Dim reader As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
    Dim file As New System.IO.StreamReader(  
        "c:\temp\SerializationOverview.xml")  
    Dim overview As Book  
    overview = CType(reader.Deserialize(file), Book)  
    Console.WriteLine(overview.Title)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="75816-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="75816-105">Compiling the Code</span></span>  
 <span data-ttu-id="75816-106">Ersetzen Sie den Dateinamen „c:\temp\SerializationOverview.xml“ durch den Namen der Datei, die die serialisierten Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="75816-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="75816-107">Weitere Informationen zum Serialisieren von Daten finden Sie unter Gewusst [wie: Schreiben von Objektdaten in eine XML-Datei (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="75816-107">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="75816-108">Die Klasse muss über einen öffentlichen Konstruktor ohne Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="75816-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="75816-109">Nur die öffentlichen Eigenschaften und Felder werden deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="75816-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="75816-110">Robuste Programmierung</span><span class="sxs-lookup"><span data-stu-id="75816-110">Robust Programming</span></span>  
 <span data-ttu-id="75816-111">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="75816-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="75816-112">Die zu serialisierende Klasse verfügt nicht über einen öffentlichen, parameterlosen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="75816-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="75816-113">Die Daten in der Datei stellen keine Daten aus der zu deserialisierenden Klasse dar.</span><span class="sxs-lookup"><span data-stu-id="75816-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
- <span data-ttu-id="75816-114">Die Datei ist nicht vorhanden (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="75816-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="75816-115">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="75816-115">.NET Framework Security</span></span>  
 <span data-ttu-id="75816-116">Überprüfen Sie immer die Eingaben, und deserialisieren Sie keine Daten aus einer nicht vertrauenswürdigen Quelle.</span><span class="sxs-lookup"><span data-stu-id="75816-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="75816-117">Das neu erstellte Objekt wird auf einem lokalen Computer mit den Berechtigungen des Codes ausgeführt, der es deserialisiert hat.</span><span class="sxs-lookup"><span data-stu-id="75816-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="75816-118">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="75816-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75816-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75816-119">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="75816-120">Gewusst wie: Schreiben von Objektdaten in eine XML-Datei (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75816-120">How to: Write Object Data to an XML File (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
- [<span data-ttu-id="75816-121">Serialisierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75816-121">Serialization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
- [<span data-ttu-id="75816-122">Visual Basic-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="75816-122">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
