---
title: "Gewusst wie: Zeilenweises Lesen einer Textdatei (Visual C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e9327181d82a97559c7be99bb76a2a93118d796b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-a-text-file-one-line-at-a-time-visual-c"></a><span data-ttu-id="6e60a-102">Gewusst wie: Zeilenweises Lesen einer Textdatei (Visual C#)</span><span class="sxs-lookup"><span data-stu-id="6e60a-102">How to: Read a Text File One Line at a Time (Visual C#)</span></span>
<span data-ttu-id="6e60a-103">Dieses Beispiel liest den Inhalt einer Textdatei Zeile pro Zeile in eine Zeichenfolge mithilfe der `ReadLine`-Methode der `StreamReader`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6e60a-103">This example reads the contents of a text file, one line at a time, into a string using the `ReadLine` method of the `StreamReader` class.</span></span> <span data-ttu-id="6e60a-104">Jede Textzeile wird in der Zeichenfolge `line` gespeichert und auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6e60a-104">Each text line is stored into the string `line` and displayed on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e60a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e60a-105">Example</span></span>  
  
```  
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine (line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6e60a-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6e60a-106">Compiling the Code</span></span>  
 <span data-ttu-id="6e60a-107">Kopieren Sie den Code, und fügen Sie ihn in die `Main`-Methode einer Konsolenanwendung ein.</span><span class="sxs-lookup"><span data-stu-id="6e60a-107">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
 <span data-ttu-id="6e60a-108">Ersetzen Sie `"c:\test.txt"` durch den tatsächlichen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="6e60a-108">Replace `"c:\test.txt"` with the actual file name.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6e60a-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="6e60a-109">Robust Programming</span></span>  
 <span data-ttu-id="6e60a-110">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="6e60a-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="6e60a-111">Die Datei ist möglicherweise nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6e60a-111">The file may not exist.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6e60a-112">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6e60a-112">.NET Framework Security</span></span>  
 <span data-ttu-id="6e60a-113">Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="6e60a-113">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="6e60a-114">Bei der Datei `myFile.cs` handelt es sich möglicherweise nicht um eine C#-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="6e60a-114">For example, the file `myFile.cs` may not be a C# source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e60a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e60a-115">See Also</span></span>  
 <span data-ttu-id="6e60a-116"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="6e60a-116"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="6e60a-117">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6e60a-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="6e60a-118">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6e60a-118">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)

