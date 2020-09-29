---
title: 'Vorgehensweise: Zeilenweises Lesen einer Textdatei (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie eine Textdatei zeilenweise lesen. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: 93645ef78f1ceb3cc4cf1d20ac73112e86957293
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178514"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-c-programming-guide"></a><span data-ttu-id="8dc30-104">Vorgehensweise: Zeilenweises Lesen einer Textdatei (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="8dc30-104">How to read a text file one line at a time (C# Programming Guide)</span></span>

<span data-ttu-id="8dc30-105">Dieses Beispiel liest den Inhalt einer Textdatei Zeile pro Zeile in eine Zeichenfolge mithilfe der `ReadLine`-Methode der `StreamReader`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8dc30-105">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="8dc30-106">Jede Textzeile wird in der Zeichenfolge `line` gespeichert und auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8dc30-106">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dc30-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8dc30-107">Example</span></span>  
  
```csharp
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine(line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8dc30-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8dc30-108">Compiling the Code</span></span>  

 <span data-ttu-id="8dc30-109">Kopieren Sie den Code, und fügen Sie ihn in die `Main`-Methode einer Konsolenanwendung ein.</span><span class="sxs-lookup"><span data-stu-id="8dc30-109">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="8dc30-110">Ersetzen Sie `"c:\test.txt"` durch den tatsächlichen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="8dc30-110">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8dc30-111">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="8dc30-111">Robust Programming</span></span>  

 <span data-ttu-id="8dc30-112">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="8dc30-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="8dc30-113">Die Datei ist möglicherweise nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="8dc30-113">The file may not exist.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="8dc30-114">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8dc30-114">.NET Security</span></span>  

 <span data-ttu-id="8dc30-115">Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="8dc30-115">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="8dc30-116">Bei der Datei `myFile.cs` handelt es sich möglicherweise nicht um eine C#-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="8dc30-116">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc30-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8dc30-117">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="8dc30-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8dc30-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8dc30-119">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8dc30-119">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
