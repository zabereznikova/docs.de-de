---
title: 'Vorgehensweise: Öffnen von Dateien mit der OpenFileDialog-Komponente'
ms.date: 02/11/2019
description: Erfahren Sie, wie Sie die OpenFileDialog-Komponente verwenden, um das Dialogfeld Windows zum Durchsuchen und Auswählen von Dateien zu öffnen.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: d571885011b0f0c723c73a417f294f30f96952f4
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904428"
---
# <a name="how-to-open-files-with-the-openfiledialog"></a><span data-ttu-id="a251b-103">Gewusst wie: Öffnen von Dateien mit OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="a251b-103">How to: Open files with the OpenFileDialog</span></span>

<span data-ttu-id="a251b-104">Die <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> -Komponente öffnet das Dialogfeld Windows zum Durchsuchen und Auswählen von Dateien.</span><span class="sxs-lookup"><span data-stu-id="a251b-104">The <xref:System.Windows.Forms.OpenFileDialog?displayProperty=nameWithType> component opens the Windows dialog box for browsing and selecting files.</span></span> <span data-ttu-id="a251b-105">Sie können die- <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> Methode verwenden oder eine Instanz der-Klasse erstellen, um die ausgewählten Dateien zu öffnen und zu lesen <xref:System.IO.StreamReader?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a251b-105">To open and read the selected files, you can use the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A?displayProperty=nameWithType> method, or create an instance of the <xref:System.IO.StreamReader?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a251b-106">In den folgenden Beispielen werden beide Vorgehensweisen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a251b-106">The following examples show both approaches.</span></span>

<span data-ttu-id="a251b-107">In .NET Framework ist für die- <xref:System.Windows.Forms.FileDialog.FileName%2A> Eigenschaft eine Berechtigungsebene erforderlich, die von der-Klasse erteilt wurde <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a251b-107">In .NET Framework, to get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="a251b-108">In den Beispielen <xref:System.Security.Permissions.FileIOPermission> wird eine Berechtigungsüberprüfung ausgeführt, und es kann eine Ausnahme aufgrund unzureichender Berechtigungen ausgelöst werden, wenn Sie in einem teilweise vertrauenswürdigen Kontext ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a251b-108">The examples run a <xref:System.Security.Permissions.FileIOPermission> permission check, and can throw an exception due to insufficient privileges if run in a partial-trust context.</span></span> <span data-ttu-id="a251b-109">Weitere Informationen finden Sie unter [Grundlagen der Code Zugriffssicherheit](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="a251b-109">For more information, see [Code access security basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="a251b-110">Sie können diese Beispiele als .NET Framework-Apps über die c#-oder Visual Basic-Befehlszeile erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="a251b-110">You can build and run these examples as .NET Framework apps from the C# or Visual Basic command line.</span></span> <span data-ttu-id="a251b-111">Weitere Informationen finden Sie unter Erstellen [über die Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) oder [Build über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="a251b-111">For more information, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>

<span data-ttu-id="a251b-112">Ab .net Core 3,0 können Sie die Beispiele auch als Windows .net Core-Apps aus einem Ordner erstellen und ausführen, der über eine .net Core Windows Forms \* \<folder name> . csproj\* -Projektdatei verfügt.</span><span class="sxs-lookup"><span data-stu-id="a251b-112">Starting with .NET Core 3.0, you can also build and run the examples as Windows .NET Core apps from a folder that has a .NET Core Windows Forms *\<folder name>.csproj* project file.</span></span>

## <a name="example-read-a-file-as-a-stream-with-streamreader"></a><span data-ttu-id="a251b-113">Beispiel: Lesen einer Datei als Stream mit StreamReader</span><span class="sxs-lookup"><span data-stu-id="a251b-113">Example: Read a file as a stream with StreamReader</span></span>  
  
<span data-ttu-id="a251b-114">Im folgenden Beispiel wird der <xref:System.Windows.Forms.Button> -Ereignishandler des Windows Forms-Steuer Elements verwendet <xref:System.Windows.Forms.Control.Click> , um <xref:System.Windows.Forms.OpenFileDialog> mit der-Methode zu öffnen <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> .</span><span class="sxs-lookup"><span data-stu-id="a251b-114">The following example uses the Windows Forms <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="a251b-115">Nachdem der Benutzer eine Datei ausgewählt und **OK**ausgewählt hat, liest eine Instanz der <xref:System.IO.StreamReader> -Klasse die Datei und zeigt ihren Inhalt im Textfeld des Formulars an.</span><span class="sxs-lookup"><span data-stu-id="a251b-115">After the user chooses a file and selects **OK**, an instance of the <xref:System.IO.StreamReader> class reads the file and displays its contents in the form's text box.</span></span> <span data-ttu-id="a251b-116">Weitere Informationen zum Lesen aus Dateistreams finden Sie unter <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> und <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a251b-116">For more information about reading from file streams, see <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> and <xref:System.IO.FileStream.Read%2A?displayProperty=nameWithType>.</span></span>  

 [!code-csharp[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#1](~/samples/snippets/winforms/open-files/example1/vb/Form1.vb)]  

## <a name="example-open-a-file-from-a-filtered-selection-with-openfile"></a><span data-ttu-id="a251b-117">Beispiel: Öffnen einer Datei aus einer gefilterten Auswahl mit OpenFile</span><span class="sxs-lookup"><span data-stu-id="a251b-117">Example: Open a file from a filtered selection with OpenFile</span></span>

<span data-ttu-id="a251b-118">Im folgenden Beispiel wird der <xref:System.Windows.Forms.Button> -Ereignishandler des-Steuer Elements verwendet <xref:System.Windows.Forms.Control.Click> , um den <xref:System.Windows.Forms.OpenFileDialog> mit einem Filter zu öffnen, der nur Textdateien anzeigt.</span><span class="sxs-lookup"><span data-stu-id="a251b-118">The following example uses the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler to open the <xref:System.Windows.Forms.OpenFileDialog> with a filter that shows only text files.</span></span> <span data-ttu-id="a251b-119">Nachdem der Benutzer eine Textdatei ausgewählt und **OK**ausgewählt hat, <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> wird die-Methode verwendet, um die Datei im Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a251b-119">After the user chooses a text file and selects **OK**, the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is used to open the file in Notepad.</span></span>

 [!code-csharp[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/cs/Form1.cs)]
 [!code-vb[OpenFileDialog#2](~/samples/snippets/winforms/open-files/example2/vb/Form1.vb)]  

## <a name="see-also"></a><span data-ttu-id="a251b-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a251b-120">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="a251b-121">OpenFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="a251b-121">OpenFileDialog component</span></span>](openfiledialog-component-windows-forms.md)
