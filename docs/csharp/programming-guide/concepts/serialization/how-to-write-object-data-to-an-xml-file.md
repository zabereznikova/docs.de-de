---
title: Schreiben von Objektdaten in eine XML-Datei (C#)
description: Dieses C#-Beispiel schreibt das Objekt aus einer Klasse mithilfe der XmlSerializer-Klasse in eine XML-Datei. Hier erfahren Sie, wie Sie den Code kompilieren.
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: 776ade1752adf15d6acce07d38120de8481a233d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178709"
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a><span data-ttu-id="217bb-104">Schreiben von Objektdaten in eine XML-Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="217bb-104">How to write object data to an XML file (C#)</span></span>

<span data-ttu-id="217bb-105">Dieses Beispiel verwendet die <xref:System.Xml.Serialization.XmlSerializer>-Klasse, um das Objekt aus einer Klasse in eine XML-Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="217bb-105">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="217bb-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="217bb-106">Example</span></span>  
  
```csharp  
public class XMLWrite  
{  
  
   static void Main(string[] args)  
    {  
        WriteXML();  
    }  
  
    public class Book  
    {  
        public String title;
    }  
  
    public static void WriteXML()  
    {  
        Book overview = new Book();  
        overview.title = "Serialization Overview";  
        System.Xml.Serialization.XmlSerializer writer =
            new System.Xml.Serialization.XmlSerializer(typeof(Book));  
  
        var path = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments) + "//SerializationOverview.xml";  
        System.IO.FileStream file = System.IO.File.Create(path);  
  
        writer.Serialize(file, overview);  
        file.Close();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="217bb-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="217bb-107">Compiling the Code</span></span>  

 <span data-ttu-id="217bb-108">Die zu serialisierende Klasse muss über einen öffentlichen Konstruktor ohne Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="217bb-108">The class being serialized must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="217bb-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="217bb-109">Robust Programming</span></span>  

 <span data-ttu-id="217bb-110">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="217bb-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="217bb-111">Die zu serialisierende Klasse verfügt nicht über einen öffentlichen, parameterlosen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="217bb-111">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="217bb-112">Die Datei ist bereits vorhanden und schreibgeschützt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="217bb-112">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="217bb-113">Der Pfad ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="217bb-113">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="217bb-114">Der Datenträger ist voll (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="217bb-114">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="217bb-115">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="217bb-115">.NET Security</span></span>  

 <span data-ttu-id="217bb-116">Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="217bb-116">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="217bb-117">Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine `Create`-Berechtigung für den Ordner.</span><span class="sxs-lookup"><span data-stu-id="217bb-117">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="217bb-118">Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung für den `Write`-Zugriff, also eine geringere Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="217bb-118">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="217bb-119">Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die `Read`-Berechtigung für eine einzelne Datei erteilt werden (anstatt `Create`-Berechtigungen für den gesamten Ordner zu gewähren).</span><span class="sxs-lookup"><span data-stu-id="217bb-119">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="217bb-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="217bb-120">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="217bb-121">Lesen von Objektdaten aus einer XML-Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="217bb-121">How to read object data from an XML file (C#)</span></span>](./how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="217bb-122">Serialisierung (C#)</span><span class="sxs-lookup"><span data-stu-id="217bb-122">Serialization (C#)</span></span>](./index.md)
