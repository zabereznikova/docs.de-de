---
title: 'Vorgehensweise: Lesen von Text aus Dateien mit einer StreamReader-Klasse (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- reading files [Visual Basic], text
- text, reading from files
- reading text from files [Visual Basic]
- files [Visual Basic], reading
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
ms.openlocfilehash: 829b515a6f99799e26da40aa8ee4ed41130dbc20
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660059"
---
# <a name="how-to-read-text-from-files-with-a-streamreader-visual-basic"></a><span data-ttu-id="1a62a-102">Vorgehensweise: Lesen von Text aus Dateien mit einer StreamReader-Klasse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a62a-102">How to: Read Text from Files with a StreamReader (Visual Basic)</span></span>
<span data-ttu-id="1a62a-103">Das `My.Computer.FileSystem`-Objekt bietet Methoden, mit denen Sie ein <xref:System.IO.TextReader>- und ein <xref:System.IO.TextWriter>-Objekt öffnen können.</span><span class="sxs-lookup"><span data-stu-id="1a62a-103">The `My.Computer.FileSystem` object provides methods to open a <xref:System.IO.TextReader> and a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="1a62a-104">Diese Methoden, `OpenTextFileWriter` und `OpenTextFileReader`, sind fortgeschrittene Methoden, die nicht in IntelliSense angezeigt werden, es sei denn, Sie wählen die Registerkarte **Alle** aus.</span><span class="sxs-lookup"><span data-stu-id="1a62a-104">These methods, `OpenTextFileWriter` and `OpenTextFileReader`, are advanced methods that do not appear in IntelliSense unless you select the **All** tab.</span></span>  
  
### <a name="to-read-a-line-from-a-file-with-a-text-reader"></a><span data-ttu-id="1a62a-105">Lesen einer Zeile aus einer Datei mit einem Textreader</span><span class="sxs-lookup"><span data-stu-id="1a62a-105">To read a line from a file with a text reader</span></span>  
  
-   <span data-ttu-id="1a62a-106">Verwenden Sie die `OpenTextFileReader`-Methode, um das <xref:System.IO.TextReader>-Objekt zu öffnen. und geben Sie die Datei an.</span><span class="sxs-lookup"><span data-stu-id="1a62a-106">Use the `OpenTextFileReader` method to open the <xref:System.IO.TextReader>, specifying the file.</span></span> <span data-ttu-id="1a62a-107">In diesem Beispiel wird die Datei `testfile.txt` geöffnet, eine Zeile daraus gelesen und in einem Meldungsfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a62a-107">This example opens the file named `testfile.txt`, reads a line from it, and displays the line in a message box.</span></span>  
  
     [!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-text-from-files-with-a-streamreader_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="1a62a-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="1a62a-108">Robust Programming</span></span>  
 <span data-ttu-id="1a62a-109">Die Datei, die gelesen wird, muss eine Textdatei sein.</span><span class="sxs-lookup"><span data-stu-id="1a62a-109">The file that is read must be a text file.</span></span>  
  
 <span data-ttu-id="1a62a-110">Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.</span><span class="sxs-lookup"><span data-stu-id="1a62a-110">Do not make decisions about the contents of the file based on the name of the file.</span></span> <span data-ttu-id="1a62a-111">Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic-Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="1a62a-111">For example, the file Form1.vb may not be a Visual Basic source file.</span></span>  
  
 <span data-ttu-id="1a62a-112">Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a62a-112">Verify all inputs before using the data in your application.</span></span> <span data-ttu-id="1a62a-113">Die Datei kann andere Inhalte als erwartet enthalten. Die Methoden zum Lesen aus der Datei können fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="1a62a-113">The contents of the file may not be what is expected, and methods to read from the file may fail.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1a62a-114">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1a62a-114">.NET Framework Security</span></span>  
 <span data-ttu-id="1a62a-115">Die Assembly benötigt zum Lesen aus dieser Datei eine von der <xref:System.Security.Permissions.FileIOPermission>-Klasse gewährte Berechtigungsebene.</span><span class="sxs-lookup"><span data-stu-id="1a62a-115">To read from a file, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission> class.</span></span> <span data-ttu-id="1a62a-116">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Code möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="1a62a-116">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="1a62a-117">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="1a62a-117">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span> <span data-ttu-id="1a62a-118">Außerdem benötigt der Benutzer Zugriff auf die Datei.</span><span class="sxs-lookup"><span data-stu-id="1a62a-118">The user also needs access to the file.</span></span> <span data-ttu-id="1a62a-119">Weitere Informationen finden Sie unter [Übersicht über die ACL-Technologie](https://msdn.microsoft.com/library/06fbf66d-6f02-4378-b863-b2f12e349045).</span><span class="sxs-lookup"><span data-stu-id="1a62a-119">For more information, see [ACL Technology Overview](https://msdn.microsoft.com/library/06fbf66d-6f02-4378-b863-b2f12e349045).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a62a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a62a-120">See also</span></span>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:System.Windows.Forms.OpenFileDialog>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>
- [<span data-ttu-id="1a62a-121">SaveFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="1a62a-121">SaveFileDialog Component</span></span>](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md)
- [<span data-ttu-id="1a62a-122">Lesen aus Dateien</span><span class="sxs-lookup"><span data-stu-id="1a62a-122">Reading from Files</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
