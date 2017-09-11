---
title: 'Gewusst wie: Lesen von Objektdaten aus einer XML-Datei (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3b9697f763a2d781c37960d46cbc7fa4536c84b4
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="39988-102">Gewusst wie: Lesen von Objektdaten aus einer XML-Datei (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39988-102">How to: Read Object Data from an XML File (Visual Basic)</span></span>
<span data-ttu-id="39988-103">In diesem Beispiel liest die Objektdaten, die zuvor in eine XML-Datei mit der <xref:System.Xml.Serialization.XmlSerializer>Klasse</xref:System.Xml.Serialization.XmlSerializer> geschrieben wurden</span><span class="sxs-lookup"><span data-stu-id="39988-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39988-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39988-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="39988-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="39988-105">Compiling the Code</span></span>  
 <span data-ttu-id="39988-106">Ersetzen Sie die Datei "c:\temp\SerializationOverview.xml" durch den Namen der Datei, die die serialisierten Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="39988-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="39988-107">Weitere Informationen zum Serialisieren von Daten finden Sie unter [Gewusst wie: Schreiben von Objektdaten in eine XML-Datei (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="39988-107">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="39988-108">Die Klasse muss über einen öffentlichen Konstruktor ohne Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="39988-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="39988-109">Nur öffentliche Eigenschaften und Felder werden deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="39988-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="39988-110">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="39988-110">Robust Programming</span></span>  
 <span data-ttu-id="39988-111">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="39988-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="39988-112">Die zu serialisierende Klasse verfügt nicht über einen öffentlichen, parameterlosen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="39988-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="39988-113">Die Daten in der Datei stellt keine Daten aus der zu deserialisierenden Klasse dar.</span><span class="sxs-lookup"><span data-stu-id="39988-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
-   <span data-ttu-id="39988-114">Die Datei ist nicht vorhanden (<xref:System.IO.IOException>).</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="39988-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="39988-115">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="39988-115">.NET Framework Security</span></span>  
 <span data-ttu-id="39988-116">Überprüfen Sie immer die Eingaben, und Deserialisieren Sie keine Daten aus einer nicht vertrauenswürdigen Quelle.</span><span class="sxs-lookup"><span data-stu-id="39988-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="39988-117">Das neu erstellte Objekt wird auf einem lokalen Computer mit den Berechtigungen des Codes, der es deserialisiert ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="39988-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="39988-118">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="39988-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39988-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39988-119">See Also</span></span>  
 <span data-ttu-id="39988-120"><xref:System.IO.StreamWriter></xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="39988-120"><xref:System.IO.StreamWriter></span></span>   
<span data-ttu-id="39988-121"> [Gewusst wie: Schreiben von Objektdaten in eine XML-Datei (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) </span><span class="sxs-lookup"><span data-stu-id="39988-121"> [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) </span></span>  
<span data-ttu-id="39988-122"> [Serialisierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md) </span><span class="sxs-lookup"><span data-stu-id="39988-122"> [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md) </span></span>  
<span data-ttu-id="39988-123"> [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)</span><span class="sxs-lookup"><span data-stu-id="39988-123"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md)</span></span>
