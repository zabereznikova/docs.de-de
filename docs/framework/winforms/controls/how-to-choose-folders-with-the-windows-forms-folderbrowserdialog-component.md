---
title: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente
description: Erfahren Sie, wie Sie die Windows Forms FolderBrowserDialog-Komponente in Windows-Anwendungen verwenden, die Sie erstellen, um Benutzer zur Auswahl eines Ordners aufzufordern.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: 11d01bbaec3b82bc221960ebab5e33ca1aa302db
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903674"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="d0ffa-103">Vorgehensweise: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d0ffa-103">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>

<span data-ttu-id="d0ffa-104">Häufig müssen Sie in von Ihnen erstellten Windows-Anwendungen Benutzer auffordern, einen Ordner auszuwählen, meistens zum Speichern einer Gruppe von Dateien.</span><span class="sxs-lookup"><span data-stu-id="d0ffa-104">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="d0ffa-105">Mit der Windows Forms- <xref:System.Windows.Forms.FolderBrowserDialog> Komponente können Sie diese Aufgabe problemlos ausführen.</span><span class="sxs-lookup"><span data-stu-id="d0ffa-105">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="d0ffa-106">So wählen Sie Ordner mit der FolderBrowserDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="d0ffa-106">To choose folders with the FolderBrowserDialog component</span></span>

1. <span data-ttu-id="d0ffa-107">Überprüfen Sie in einer-Prozedur die <xref:System.Windows.Forms.FolderBrowserDialog> -Eigenschaft der Komponente, <xref:System.Windows.Forms.Form.DialogResult%2A> um zu sehen, wie das Dialogfeld geschlossen wurde, und erhalten Sie den Wert der <xref:System.Windows.Forms.FolderBrowserDialog> -Eigenschaft der Komponente <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> .</span><span class="sxs-lookup"><span data-stu-id="d0ffa-107">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>

2. <span data-ttu-id="d0ffa-108">Wenn Sie den obersten Ordner festlegen müssen, der in der Strukturansicht des Dialog Felds angezeigt wird, legen Sie die- <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> Eigenschaft fest, die ein Member der- <xref:System.Environment.SpecialFolder> Enumeration annimmt.</span><span class="sxs-lookup"><span data-stu-id="d0ffa-108">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>

3. <span data-ttu-id="d0ffa-109">Darüber hinaus können Sie die- <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> Eigenschaft festlegen, die die Text Zeichenfolge angibt, die am oberen Rand der Ordner-Browser Strukturansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d0ffa-109">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>

    <span data-ttu-id="d0ffa-110">Im folgenden Beispiel wird die- <xref:System.Windows.Forms.FolderBrowserDialog> Komponente verwendet, um einen Ordner auszuwählen, ähnlich dem, wenn Sie ein Projekt in Visual Studio erstellen und zum Auswählen eines Ordners aufgefordert werden, in dem Sie gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d0ffa-110">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="d0ffa-111">In diesem Beispiel wird der Ordnername in einem-Steuerelement <xref:System.Windows.Forms.TextBox> auf dem Formular angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0ffa-111">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="d0ffa-112">Es empfiehlt sich, die Position in einem bearbeitbaren Bereich, z. b. einem <xref:System.Windows.Forms.TextBox> Steuerelement, zu platzieren, damit Benutzer Ihre Auswahl im Falle von Fehlern oder anderen Problemen bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="d0ffa-112">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="d0ffa-113">In diesem Beispiel wird ein Formular mit einer <xref:System.Windows.Forms.FolderBrowserDialog> -Komponente und einem-Steuerelement angenommen <xref:System.Windows.Forms.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="d0ffa-113">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>

    ```vb
    Public Sub ChooseFolder()
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then
            TextBox1.Text = FolderBrowserDialog1.SelectedPath
        End If
    End Sub
    ```

    ```csharp
    public void ChooseFolder()
    {
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)
        {
            textBox1.Text = folderBrowserDialog1.SelectedPath;
        }
    }
    ```

    ```cpp
    public:
       void ChooseFolder()
       {
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)
          {
             textBox1->Text = folderBrowserDialog1->SelectedPath;
          }
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="d0ffa-114">Um diese Klasse verwenden zu können, benötigt die Assembly eine Berechtigungsebene, die von der-Eigenschaft gewährt wird <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> , die Teil der- <xref:System.Security.Permissions.FileIOPermissionAccess> Enumeration ist.</span><span class="sxs-lookup"><span data-stu-id="d0ffa-114">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="d0ffa-115">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="d0ffa-115">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="d0ffa-116">Weitere Informationen finden Sie unter [Code Access Security Basics](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="d0ffa-116">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="d0ffa-117">Informationen zum Speichern von Dateien finden Sie unter [Gewusst wie: Speichern von Dateien mit der SaveFileDialog-Komponente](how-to-save-files-using-the-savefiledialog-component.md).</span><span class="sxs-lookup"><span data-stu-id="d0ffa-117">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](how-to-save-files-using-the-savefiledialog-component.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d0ffa-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0ffa-118">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="d0ffa-119">Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d0ffa-119">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="d0ffa-120">FolderBrowserDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="d0ffa-120">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
