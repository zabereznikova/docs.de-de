---
title: 'Vorgehensweise: Wählen Sie Ordner mit der FolderBrowserDialog-Komponente in Windows Forms'
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
ms.openlocfilehash: ea5fdc9708d8e896eb66fa42f64cac672baff08b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724556"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="4d9c6-102">Vorgehensweise: Wählen Sie Ordner mit der FolderBrowserDialog-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4d9c6-102">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>
<span data-ttu-id="4d9c6-103">Häufig müssen Sie in von Ihnen erstellten Windows-Anwendungen Benutzer auffordern, einen Ordner auszuwählen, meistens zum Speichern einer Gruppe von Dateien.</span><span class="sxs-lookup"><span data-stu-id="4d9c6-103">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="4d9c6-104">Die Windows-Formulare <xref:System.Windows.Forms.FolderBrowserDialog> Komponente können Sie diese Aufgabe problemlos erledigen.</span><span class="sxs-lookup"><span data-stu-id="4d9c6-104">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="4d9c6-105">So wählen Sie Ordner mit der FolderBrowserDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="4d9c6-105">To choose folders with the FolderBrowserDialog component</span></span>  
  
1.  <span data-ttu-id="4d9c6-106">Überprüfen Sie in einer Prozedur die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente <xref:System.Windows.Forms.Form.DialogResult%2A> Eigenschaft, um festzustellen, wie Sie das Dialogfeld geschlossen wurde, und rufen Sie den Wert von der <xref:System.Windows.Forms.FolderBrowserDialog> Komponente <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4d9c6-106">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>  
  
2.  <span data-ttu-id="4d9c6-107">Wenn Sie den obersten Ordner, die in der Strukturansicht des Dialogfelds angezeigt werden müssen, legen die <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> -Eigenschaft, die einen Member verwendet die <xref:System.Environment.SpecialFolder> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4d9c6-107">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>  
  
3.  <span data-ttu-id="4d9c6-108">Darüber hinaus können Sie festlegen der <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> Eigenschaft, die angibt, die Text-Zeichenfolge, wird am oberen Rand der Ordnerbrowser Strukturansicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d9c6-108">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>  
  
     <span data-ttu-id="4d9c6-109">Im folgenden Beispiel wird die <xref:System.Windows.Forms.FolderBrowserDialog> Komponente wird verwendet, um Wählen Sie einen Ordner, ähnlich wie wenn Sie ein Projekt in Visual Studio erstellen und werden aufgefordert, einen Ordner zum Speichern auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4d9c6-109">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="4d9c6-110">In diesem Beispiel ist der Name des Ordners wird angezeigt einem <xref:System.Windows.Forms.TextBox> Steuerelement im Formular.</span><span class="sxs-lookup"><span data-stu-id="4d9c6-110">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="4d9c6-111">Es ist eine gute Idee, platzieren den Speicherort in einem bearbeitbaren Bereich, z. B. eine <xref:System.Windows.Forms.TextBox> zu steuern, sodass Benutzer die Auswahl bei einem Fehler oder andere Probleme bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="4d9c6-111">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="4d9c6-112">In diesem Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.FolderBrowserDialog> Komponente und eine <xref:System.Windows.Forms.TextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4d9c6-112">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
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
    >  <span data-ttu-id="4d9c6-113">Um diese Klasse verwenden zu können, benötigt Ihre Assembly eine Berechtigungsebene gewährt durch die <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> -Eigenschaft, die Teil von der <xref:System.Security.Permissions.FileIOPermissionAccess> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4d9c6-113">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="4d9c6-114">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="4d9c6-114">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="4d9c6-115">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c6-115">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>  
  
 <span data-ttu-id="4d9c6-116">Weitere Informationen zum Speichern von Dateien, finden Sie unter [Vorgehensweise: Speichern von Dateien mit der SaveFileDialog-Komponente](how-to-save-files-using-the-savefiledialog-component.md).</span><span class="sxs-lookup"><span data-stu-id="4d9c6-116">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](how-to-save-files-using-the-savefiledialog-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d9c6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d9c6-117">See also</span></span>
- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="4d9c6-118">Übersicht über die FolderBrowserDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4d9c6-118">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="4d9c6-119">FolderBrowserDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="4d9c6-119">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
