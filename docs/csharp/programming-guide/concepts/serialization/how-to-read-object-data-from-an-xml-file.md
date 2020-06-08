---
title: 'Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei (C#)'
ms.date: 07/20/2015
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
ms.openlocfilehash: e2365d1260d3f6e239f294b2af3399c2fb659575
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241876"
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a><span data-ttu-id="09a41-102">Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="09a41-102">How to read object data from an XML file (C#)</span></span>
<span data-ttu-id="09a41-103">In diesem Beispiel werden Objektdaten gelesen, die zuvor mithilfe der <xref:System.Xml.Serialization.XmlSerializer>-Klasse in eine XML-Datei geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="09a41-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09a41-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="09a41-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="09a41-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="09a41-105">Compiling the Code</span></span>  
<span data-ttu-id="09a41-106">Ersetzen Sie den Dateinamen „c:\temp\SerializationOverview.xml“ durch den Namen der Datei, die die serialisierten Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="09a41-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="09a41-107">Weitere Informationen zum Serialisieren von Daten finden Sie unter [Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei (C#)](./how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="09a41-107">For more information about serializing data, see [How to write object data to an XML file (C#)](./how-to-write-object-data-to-an-xml-file.md).</span></span>
  
 <span data-ttu-id="09a41-108">Die Klasse muss über einen öffentlichen Konstruktor ohne Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="09a41-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="09a41-109">Nur die öffentlichen Eigenschaften und Felder werden deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="09a41-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="09a41-110">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="09a41-110">Robust Programming</span></span>  
 <span data-ttu-id="09a41-111">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="09a41-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="09a41-112">Die zu serialisierende Klasse verfügt nicht über einen öffentlichen, parameterlosen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="09a41-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="09a41-113">Die Daten in der Datei stellen keine Daten aus der zu deserialisierenden Klasse dar.</span><span class="sxs-lookup"><span data-stu-id="09a41-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
- <span data-ttu-id="09a41-114">Die Datei ist nicht vorhanden (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="09a41-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="09a41-115">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="09a41-115">.NET Security</span></span>  
 <span data-ttu-id="09a41-116">Überprüfen Sie immer die Eingaben, und deserialisieren Sie keine Daten aus einer nicht vertrauenswürdigen Quelle.</span><span class="sxs-lookup"><span data-stu-id="09a41-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="09a41-117">Das neu erstellte Objekt wird auf einem lokalen Computer mit den Berechtigungen des Codes ausgeführt, der es deserialisiert hat.</span><span class="sxs-lookup"><span data-stu-id="09a41-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="09a41-118">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="09a41-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a41-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09a41-119">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="09a41-120">Schreiben von Objektdaten in eine XML-Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="09a41-120">How to write object data to an XML file (C#)</span></span>](./how-to-write-object-data-to-an-xml-file.md)
- [<span data-ttu-id="09a41-121">Serialisierung (C#)</span><span class="sxs-lookup"><span data-stu-id="09a41-121">Serialization (C#)</span></span>](./index.md)
- [<span data-ttu-id="09a41-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="09a41-122">C# Programming Guide</span></span>](../../index.md)
