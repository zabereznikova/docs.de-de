---
title: 'Vorgehensweise: Zeilenweises Lesen einer Textdatei (C#-Programmierleitfaden)'
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: a6af48cdacd836465d776a3fd4e1d17aa0298b77
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75635339"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-c-programming-guide"></a><span data-ttu-id="c8492-102">Vorgehensweise: Zeilenweises Lesen einer Textdatei (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="c8492-102">How to read a text file one line at a time (C# Programming Guide)</span></span>
<span data-ttu-id="c8492-103">Dieses Beispiel liest den Inhalt einer Textdatei Zeile pro Zeile in eine Zeichenfolge mithilfe der `ReadLine`-Methode der `StreamReader`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="c8492-103">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="c8492-104">Jede Textzeile wird in der Zeichenfolge `line` gespeichert und auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c8492-104">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8492-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8492-105">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="c8492-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c8492-106">Compiling the Code</span></span>  
 <span data-ttu-id="c8492-107">Kopieren Sie den Code, und fügen Sie ihn in die `Main`-Methode einer Konsolenanwendung ein.</span><span class="sxs-lookup"><span data-stu-id="c8492-107">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="c8492-108">Ersetzen Sie `"c:\test.txt"` durch den tatsächlichen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="c8492-108">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c8492-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="c8492-109">Robust Programming</span></span>  
 <span data-ttu-id="c8492-110">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="c8492-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="c8492-111">Die Datei ist möglicherweise nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c8492-111">The file may not exist.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c8492-112">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c8492-112">.NET Framework Security</span></span>  
 <span data-ttu-id="c8492-113">Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="c8492-113">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="c8492-114">Bei der Datei `myFile.cs` handelt es sich möglicherweise nicht um eine C#-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="c8492-114">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8492-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8492-115">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="c8492-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c8492-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c8492-117">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c8492-117">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
