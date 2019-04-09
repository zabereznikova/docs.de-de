---
title: 'Vorgehensweise: Öffnen von Dateien mit der OpenFileDialog-Komponente'
ms.date: 02/11/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: 7f4e96f1714a182647665f12e29d38f2b8037478
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159106"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="137f2-102">Vorgehensweise: Mit der OpenFileDialog geöffneten Dateien</span><span class="sxs-lookup"><span data-stu-id="137f2-102">How to: Open files with the OpenFileDialog</span></span> 

<span data-ttu-id="137f2-103">Die <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> Komponente Öffnet das Dialogfeld "Windows", für das Durchsuchen und Auswählen von Dateien.</span><span class="sxs-lookup"><span data-stu-id="137f2-103">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="137f2-104">Öffnen und die ausgewählte Dateien lesen, können Sie die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> -Methode, oder erstellen Sie eine Instanz von der <xref:System.IO.StreamReader?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="137f2-104">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="137f2-105">In den folgenden Beispielen werden beide Ansätze gezeigt.</span><span class="sxs-lookup"><span data-stu-id="137f2-105">The following examples show both approaches.</span></span> 

<span data-ttu-id="137f2-106">In .NET Framework zum Abrufen oder Festlegen der <xref:System.Windows.Forms.FileDialog.FileName%2A> Eigenschaft benötigt eine Berechtigungsebene gewährt, durch die <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="137f2-106">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="137f2-107">Ausführen der Beispiele ein <xref:System.Security.Permissions.FileIOPermission> Berechtigung überprüfen, und kann aufgrund fehlender Berechtigungen eine Ausnahme auslösen, wenn in einer teilweise vertrauenswürdigen Kontext ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="137f2-107">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="137f2-108">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="137f2-108">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="137f2-109">Können Sie erstellen und Ausführen dieser Beispiele als .NET Framework-apps aus dem C# oder Visual Basic über die Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="137f2-109">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="137f2-110">Weitere Informationen finden Sie unter [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="137f2-110">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span> 

<span data-ttu-id="137f2-111">Ab .NET Core 3.0, Sie können auch erstellen und Ausführen der Beispiele als Windows .NET Core-apps aus einem Ordner, die eine .NET Core Windows Forms  *\<Ordnername > .csproj* Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="137f2-111">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span> 

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="137f2-112">Beispiel: Lesen einer Datei als Stream mit StreamReader</span><span class="sxs-lookup"><span data-stu-id="137f2-112">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="137f2-113">Im folgenden Beispiel wird die Windows-Formulare <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> -Ereignishandler zum Öffnen der <xref:System.Windows.Forms.OpenFileDialog> mit der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="137f2-113">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="137f2-114">Nachdem der Benutzer eine Datei wählt und wählt **OK**, eine Instanz von der <xref:System.IO.StreamReader> Klasse liest die Datei und ihr Inhalt im Textfeld des Formulars angezeigt.</span><span class="sxs-lookup"><span data-stu-id="137f2-114">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="137f2-115">Weitere Informationen zum Lesen aus Dateistreams finden Sie unter <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> und <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="137f2-115">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="137f2-116">Beispiel: Öffnen Sie eine Datei aus einer gefilterten mit OpenFile-Auswahl</span><span class="sxs-lookup"><span data-stu-id="137f2-116">Example: Open a file from a filtered selection with OpenFile</span></span> 

<span data-ttu-id="137f2-117">Im folgenden Beispiel wird die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> -Ereignishandler zum Öffnen der <xref:System.Windows.Forms.OpenFileDialog> mit einem Filter, die nur-Text-Dateien anzeigt.</span><span class="sxs-lookup"><span data-stu-id="137f2-117">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="137f2-118">Nachdem der Benutzer eine Textdatei wählt, und wählt **OK**, <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> Methode wird verwendet, um die Datei im Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="137f2-118">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="137f2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="137f2-119">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="137f2-120">OpenFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="137f2-120">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
