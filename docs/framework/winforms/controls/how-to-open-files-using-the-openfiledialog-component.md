---
title: 'Gewusst wie: Öffnen von Dateien mit der OpenFileDialog-Komponente'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: ca69de19ab1b9ae387002898145fe99e35a7b6b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182131"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="37746-102">Gewusst wie: Öffnen von Dateien mit dem OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="37746-102">How to: Open files with the OpenFileDialog</span></span>

<span data-ttu-id="37746-103">Die <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> Komponente öffnet das Windows-Dialogfeld zum Durchsuchen und Auswählen von Dateien.</span><span class="sxs-lookup"><span data-stu-id="37746-103">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="37746-104">Um die ausgewählten Dateien zu öffnen <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> und zu lesen, können <xref:System.IO.StreamReader?displayProperty=nameWithType> Sie die Methode verwenden oder eine Instanz der Klasse erstellen.</span><span class="sxs-lookup"><span data-stu-id="37746-104">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="37746-105">Die folgenden Beispiele zeigen beide Ansätze.</span><span class="sxs-lookup"><span data-stu-id="37746-105">The following examples show both approaches.</span></span>

<span data-ttu-id="37746-106">In .NET Framework erfordert das <xref:System.Windows.Forms.FileDialog.FileName%2A> Abrufen oder Festlegen der <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> Eigenschaft eine von der Klasse gewährte Berechtigungsstufe.</span><span class="sxs-lookup"><span data-stu-id="37746-106">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="37746-107">Die Beispiele <xref:System.Security.Permissions.FileIOPermission> führen eine Berechtigungsprüfung aus und können eine Ausnahme aufgrund unzureichender Berechtigungen auslösen, wenn sie in einem Kontext mit teilweiser Vertrauenswürdigkeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="37746-107">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="37746-108">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="37746-108">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="37746-109">Sie können diese Beispiele als .NET Framework-Apps über die Befehlszeile "C" oder "Visual Basic" erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="37746-109">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="37746-110">Weitere Informationen finden Sie unter [Befehlszeilenerstellung mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [Build über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="37746-110">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

<span data-ttu-id="37746-111">Ab .NET Core 3.0 können Sie die Beispiele auch als Windows .NET Core-Apps aus einem Ordner mit dem Ordnernamen .NET Core Windows Forms \* \<>.csproj-Projektdatei\* erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="37746-111">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="37746-112">Beispiel: Lesen einer Datei als Stream mit StreamReader</span><span class="sxs-lookup"><span data-stu-id="37746-112">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="37746-113">Im folgenden Beispiel wird <xref:System.Windows.Forms.Button> der <xref:System.Windows.Forms.Control.Click> Ereignishandler des <xref:System.Windows.Forms.OpenFileDialog> Windows <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Forms-Steuerelements verwendet, um den mit der Methode zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="37746-113">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="37746-114">Nachdem der Benutzer eine Datei ausgewählt und **OK** <xref:System.IO.StreamReader> ausgewählt hat, liest eine Instanz der Klasse die Datei und zeigt deren Inhalt im Textfeld des Formulars an.</span><span class="sxs-lookup"><span data-stu-id="37746-114">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="37746-115">Weitere Informationen zum Lesen aus <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> Dateistreams finden Sie unter und <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="37746-115">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="37746-116">Beispiel: Öffnen einer Datei aus einer gefilterten Auswahl mit OpenFile</span><span class="sxs-lookup"><span data-stu-id="37746-116">Example: Open a file from a filtered selection with OpenFile</span></span>

<span data-ttu-id="37746-117">Im folgenden Beispiel <xref:System.Windows.Forms.Button> wird <xref:System.Windows.Forms.Control.Click> der Ereignishandler <xref:System.Windows.Forms.OpenFileDialog> des Steuerelements verwendet, um den mit einem Filter zu öffnen, der nur Textdateien anzeigt.</span><span class="sxs-lookup"><span data-stu-id="37746-117">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="37746-118">Nachdem der Benutzer eine Textdatei **OK**ausgewählt und <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> OK ausgewählt hat, wird die Methode zum Öffnen der Datei in Notepad verwendet.</span><span class="sxs-lookup"><span data-stu-id="37746-118">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="37746-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="37746-119">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="37746-120">OpenFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="37746-120">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
