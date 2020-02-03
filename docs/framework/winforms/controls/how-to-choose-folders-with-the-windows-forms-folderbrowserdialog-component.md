---
title: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente
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
ms.openlocfilehash: 313388442101f341cfed366143f3c9669fb45cbd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742231"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="6f43d-102">Gewusst wie: Auswählen von Ordnern mit der FolderBrowserDialog-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f43d-102">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>

<span data-ttu-id="6f43d-103">Häufig müssen Sie in von Ihnen erstellten Windows-Anwendungen Benutzer auffordern, einen Ordner auszuwählen, meistens zum Speichern einer Gruppe von Dateien.</span><span class="sxs-lookup"><span data-stu-id="6f43d-103">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="6f43d-104">Mit der Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog>-Komponente können Sie diese Aufgabe problemlos erledigen.</span><span class="sxs-lookup"><span data-stu-id="6f43d-104">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="6f43d-105">So wählen Sie Ordner mit der FolderBrowserDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="6f43d-105">To choose folders with the FolderBrowserDialog component</span></span>

1. <span data-ttu-id="6f43d-106">Aktivieren Sie in einer Prozedur die <xref:System.Windows.Forms.Form.DialogResult%2A>-Eigenschaft der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente, um zu sehen, wie das Dialogfeld geschlossen wurde, und den Wert der <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>-Eigenschaft der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6f43d-106">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>

2. <span data-ttu-id="6f43d-107">Wenn Sie den obersten Ordner festlegen müssen, der in der Strukturansicht des Dialog Felds angezeigt wird, legen Sie die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>-Eigenschaft fest, die ein Member der <xref:System.Environment.SpecialFolder>-Enumeration annimmt.</span><span class="sxs-lookup"><span data-stu-id="6f43d-107">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>

3. <span data-ttu-id="6f43d-108">Außerdem können Sie die <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A>-Eigenschaft festlegen, die die Text Zeichenfolge angibt, die am oberen Rand der Ordner-Browser Strukturansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6f43d-108">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>

    <span data-ttu-id="6f43d-109">Im folgenden Beispiel wird die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente verwendet, um einen Ordner auszuwählen, ähnlich dem, wenn Sie ein Projekt in Visual Studio erstellen und zum Auswählen eines Ordners aufgefordert werden, in dem Sie gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6f43d-109">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="6f43d-110">In diesem Beispiel wird der Ordnername in einem <xref:System.Windows.Forms.TextBox>-Steuerelement auf dem Formular angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f43d-110">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="6f43d-111">Es empfiehlt sich, den Speicherort in einen bearbeitbaren Bereich zu versetzen, wie z. b. ein <xref:System.Windows.Forms.TextBox> Steuerelement, damit Benutzer die Auswahl im Falle von Fehlern oder anderen Problemen bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="6f43d-111">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="6f43d-112">In diesem Beispiel wird davon ausgegangen, dass ein Formular mit einer <xref:System.Windows.Forms.FolderBrowserDialog> Komponente und einem <xref:System.Windows.Forms.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6f43d-112">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>

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
    > <span data-ttu-id="6f43d-113">Um diese Klasse verwenden zu können, benötigt die Assembly eine Berechtigungsebene, die von der <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>-Eigenschaft gewährt wird, die Teil der <xref:System.Security.Permissions.FileIOPermissionAccess>-Enumeration ist.</span><span class="sxs-lookup"><span data-stu-id="6f43d-113">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="6f43d-114">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="6f43d-114">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="6f43d-115">Weitere Informationen finden Sie unter [Code Access Security Basics](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="6f43d-115">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="6f43d-116">Informationen zum Speichern von Dateien finden Sie unter [Gewusst wie: Speichern von Dateien mit der SaveFileDialog-Komponente](how-to-save-files-using-the-savefiledialog-component.md).</span><span class="sxs-lookup"><span data-stu-id="6f43d-116">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](how-to-save-files-using-the-savefiledialog-component.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6f43d-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f43d-117">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="6f43d-118">Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6f43d-118">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="6f43d-119">FolderBrowserDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="6f43d-119">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
