---
title: 'Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei (C#)'
description: Dieses C#-Beispiel liest Objektdaten, die zuvor mithilfe der XmlSerializer-Klasse in eine XML-Datei geschrieben wurden.
ms.date: 07/20/2015
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
ms.openlocfilehash: 525a93812279756b3802d43d85bb5e61d8f7415e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302788"
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a><span data-ttu-id="f69e5-103">Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="f69e5-103">How to read object data from an XML file (C#)</span></span>
<span data-ttu-id="f69e5-104">In diesem Beispiel werden Objektdaten gelesen, die zuvor mithilfe der <xref:System.Xml.Serialization.XmlSerializer>-Klasse in eine XML-Datei geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="f69e5-104">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f69e5-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f69e5-105">Example</span></span>  
  
```csharp  
public class Book  
{  
    public String title;  
}
  
public void ReadXML()  
{  
    // First write something so that there is something to read ...  
    var b = new Book { title = "Serialization Overview" };  
    var writer = new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    var wfile = new System.IO.StreamWriter(@"c:\temp\SerializationOverview.xml");  
    writer.Serialize(wfile, b);  
    wfile.Close();  
  
    // Now we can read the serialized book ...  
    System.Xml.Serialization.XmlSerializer reader =
        new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    System.IO.StreamReader file = new System.IO.StreamReader(  
        @"c:\temp\SerializationOverview.xml");  
    Book overview =  (Book)reader.Deserialize(file);  
    file.Close();  
  
    Console.WriteLine(overview.title);  
  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f69e5-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f69e5-106">Compiling the Code</span></span>  
<span data-ttu-id="f69e5-107">Ersetzen Sie den Dateinamen „c:\temp\SerializationOverview.xml“ durch den Namen der Datei, die die serialisierten Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="f69e5-107">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="f69e5-108">Weitere Informationen zum Serialisieren von Daten finden Sie unter [Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei (C#)](./how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="f69e5-108">For more information about serializing data, see [How to write object data to an XML file (C#)](./how-to-write-object-data-to-an-xml-file.md).</span></span>
  
 <span data-ttu-id="f69e5-109">Die Klasse muss über einen öffentlichen Konstruktor ohne Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="f69e5-109">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="f69e5-110">Nur die öffentlichen Eigenschaften und Felder werden deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="f69e5-110">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f69e5-111">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="f69e5-111">Robust Programming</span></span>  
 <span data-ttu-id="f69e5-112">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="f69e5-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="f69e5-113">Die zu serialisierende Klasse verfügt nicht über einen öffentlichen, parameterlosen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="f69e5-113">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="f69e5-114">Die Daten in der Datei stellen keine Daten aus der zu deserialisierenden Klasse dar.</span><span class="sxs-lookup"><span data-stu-id="f69e5-114">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
- <span data-ttu-id="f69e5-115">Die Datei ist nicht vorhanden (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="f69e5-115">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="f69e5-116">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f69e5-116">.NET Security</span></span>  
 <span data-ttu-id="f69e5-117">Überprüfen Sie immer die Eingaben, und deserialisieren Sie keine Daten aus einer nicht vertrauenswürdigen Quelle.</span><span class="sxs-lookup"><span data-stu-id="f69e5-117">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="f69e5-118">Das neu erstellte Objekt wird auf einem lokalen Computer mit den Berechtigungen des Codes ausgeführt, der es deserialisiert hat.</span><span class="sxs-lookup"><span data-stu-id="f69e5-118">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="f69e5-119">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="f69e5-119">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f69e5-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f69e5-120">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="f69e5-121">Schreiben von Objektdaten in eine XML-Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="f69e5-121">How to write object data to an XML file (C#)</span></span>](./how-to-write-object-data-to-an-xml-file.md)
- [<span data-ttu-id="f69e5-122">Serialisierung (C#)</span><span class="sxs-lookup"><span data-stu-id="f69e5-122">Serialization (C#)</span></span>](./index.md)
- [<span data-ttu-id="f69e5-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f69e5-123">C# Programming Guide</span></span>](../../index.md)
