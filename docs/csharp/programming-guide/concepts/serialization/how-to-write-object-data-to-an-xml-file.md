---
title: Schreiben von Objektdaten in eine XML-Datei (C#)
description: Dieses C#-Beispiel schreibt das Objekt aus einer Klasse mithilfe der XmlSerializer-Klasse in eine XML-Datei. Hier erfahren Sie, wie Sie den Code kompilieren.
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: c88a85f8bc65a195f404dab6aa39675bac7e4f84
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303126"
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a><span data-ttu-id="4d20b-104">Schreiben von Objektdaten in eine XML-Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="4d20b-104">How to write object data to an XML file (C#)</span></span>
<span data-ttu-id="4d20b-105">Dieses Beispiel verwendet die <xref:System.Xml.Serialization.XmlSerializer>-Klasse, um das Objekt aus einer Klasse in eine XML-Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="4d20b-105">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d20b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d20b-106">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="4d20b-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4d20b-107">Compiling the Code</span></span>  
 <span data-ttu-id="4d20b-108">Die zu serialisierende Klasse muss über einen öffentlichen Konstruktor ohne Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="4d20b-108">The class being serialized must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4d20b-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="4d20b-109">Robust Programming</span></span>  
 <span data-ttu-id="4d20b-110">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="4d20b-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="4d20b-111">Die zu serialisierende Klasse verfügt nicht über einen öffentlichen, parameterlosen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="4d20b-111">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="4d20b-112">Die Datei ist bereits vorhanden und schreibgeschützt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="4d20b-112">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="4d20b-113">Der Pfad ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="4d20b-113">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="4d20b-114">Der Datenträger ist voll (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="4d20b-114">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="4d20b-115">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4d20b-115">.NET Security</span></span>  
 <span data-ttu-id="4d20b-116">Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4d20b-116">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="4d20b-117">Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine `Create`-Berechtigung für den Ordner.</span><span class="sxs-lookup"><span data-stu-id="4d20b-117">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="4d20b-118">Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung für den `Write`-Zugriff, also eine geringere Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="4d20b-118">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="4d20b-119">Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die `Read`-Berechtigung für eine einzelne Datei erteilt werden (anstatt `Create`-Berechtigungen für den gesamten Ordner zu gewähren).</span><span class="sxs-lookup"><span data-stu-id="4d20b-119">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d20b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d20b-120">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="4d20b-121">Lesen von Objektdaten aus einer XML-Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="4d20b-121">How to read object data from an XML file (C#)</span></span>](./how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="4d20b-122">Serialisierung (C#)</span><span class="sxs-lookup"><span data-stu-id="4d20b-122">Serialization (C#)</span></span>](./index.md)
