---
title: 'Vorgehensweise: Speichern von Dateien mit dem RichTextBox-Steuerelement von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
ms.openlocfilehash: c5d88e4942d96ee12e8b9f40156090c874386668
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046267"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="b5397-102">Vorgehensweise: Speichern von Dateien mit dem RichTextBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b5397-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="b5397-103">Das Windows Forms <xref:System.Windows.Forms.RichTextBox> Steuerelement kann die angezeigten Informationen in einem von mehreren Formaten schreiben:</span><span class="sxs-lookup"><span data-stu-id="b5397-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>

- <span data-ttu-id="b5397-104">Nur-Text</span><span class="sxs-lookup"><span data-stu-id="b5397-104">Plain text</span></span>

- <span data-ttu-id="b5397-105">Unicode-nur-Text</span><span class="sxs-lookup"><span data-stu-id="b5397-105">Unicode plain text</span></span>

- <span data-ttu-id="b5397-106">Rich-Text-Format (RTF)</span><span class="sxs-lookup"><span data-stu-id="b5397-106">Rich-Text Format (RTF)</span></span>

- <span data-ttu-id="b5397-107">RTF mit Leerzeichen anstelle von OLE-Objekten</span><span class="sxs-lookup"><span data-stu-id="b5397-107">RTF with spaces in place of OLE objects</span></span>

- <span data-ttu-id="b5397-108">Klartext mit Textdarstellung von OLE-Objekten</span><span class="sxs-lookup"><span data-stu-id="b5397-108">Plain text with a textual representation of OLE objects</span></span>

<span data-ttu-id="b5397-109">Um eine Datei zu speichern, wird <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> die-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b5397-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="b5397-110">Sie können auch die **SaveFile** -Methode verwenden, um Daten in einem Stream zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b5397-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="b5397-111">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="b5397-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>

### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="b5397-112">So speichern Sie den Inhalt des Steuer Elements in einer Datei</span><span class="sxs-lookup"><span data-stu-id="b5397-112">To save the contents of the control to a file</span></span>

1. <span data-ttu-id="b5397-113">Bestimmen Sie den Pfad der zu speichernden Datei.</span><span class="sxs-lookup"><span data-stu-id="b5397-113">Determine the path of the file to be saved.</span></span>

    <span data-ttu-id="b5397-114">Um dies in einer realen Anwendung zu erreichen, verwenden Sie in der Regel die <xref:System.Windows.Forms.SaveFileDialog> -Komponente.</span><span class="sxs-lookup"><span data-stu-id="b5397-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="b5397-115">Eine Übersicht finden Sie unter [Übersicht über die SaveFileDialog-Komponente](savefiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b5397-115">For an overview, see [SaveFileDialog Component Overview](savefiledialog-component-overview-windows-forms.md).</span></span>

2. <span data-ttu-id="b5397-116">Ruft die <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> -Methode <xref:System.Windows.Forms.RichTextBox> des-Steuer Elements auf und gibt die zu speichernde Datei und optional einen Dateityp an.</span><span class="sxs-lookup"><span data-stu-id="b5397-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="b5397-117">Wenn Sie die Methode mit einem Dateinamen als einziges Argument aufzurufen, wird die Datei als RTF gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b5397-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="b5397-118">Rufen Sie zum Angeben eines anderen Dateityps die Methode mit dem Wert der <xref:System.Windows.Forms.RichTextBoxStreamType> -Enumeration als zweites Argument auf.</span><span class="sxs-lookup"><span data-stu-id="b5397-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>

    <span data-ttu-id="b5397-119">Im folgenden Beispiel ist der Pfad, der für den Speicherort der Rich-Text-Datei festgelegt ist, der Ordner " **eigene** Dateien".</span><span class="sxs-lookup"><span data-stu-id="b5397-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="b5397-120">Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass die meisten Computer unter dem Windows-Betriebssystem diesen Ordner enthalten.</span><span class="sxs-lookup"><span data-stu-id="b5397-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="b5397-121">Wenn Sie diesen Speicherort auswählen, können Benutzer mit minimalen System Zugriffsebenen die Anwendung sicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="b5397-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="b5397-122">Im folgenden Beispiel wird davon ausgegangen, dass <xref:System.Windows.Forms.RichTextBox> ein Formular bereits hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="b5397-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>

    ```vb
    Public Sub SaveFile()
       ' You should replace the bold file name in the
       ' sample below with a file name of your own choosing.
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.Personal) _
       & "\Testdoc.rtf", _
          RichTextBoxStreamType.RichNoOleObjs)
    End Sub
    ```

    ```csharp
    public void SaveFile()
    {
       // You should replace the bold file name in the
       // sample below with a file name of your own choosing.
       // Note the escape character used (@) when specifying the path.
       richTextBox1.SaveFile(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\Testdoc.rtf",
          RichTextBoxStreamType.RichNoOleObjs);
    }
    ```

    ```cpp
    public:
       void SaveFile()
       {
          // You should replace the bold file name in the
          // sample below with a file name of your own choosing.
          richTextBox1->SaveFile(String::Concat
             (System::Environment::GetFolderPath
             (System::Environment::SpecialFolder::Personal),
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="b5397-123">Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b5397-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="b5397-124">Wenn eine Anwendung eine Datei erstellen muss, muss diese Anwendung Zugriff auf den Ordner erstellen.</span><span class="sxs-lookup"><span data-stu-id="b5397-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="b5397-125">Berechtigungen werden mithilfe von Zugriffssteuerungslisten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b5397-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="b5397-126">Wenn die Datei bereits vorhanden ist, benötigt die Anwendung nur Schreibzugriff, eine geringere Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="b5397-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="b5397-127">Wenn möglich, ist es sicherer, die Datei während der Bereitstellung zu erstellen, und nur Lesezugriff auf eine einzelne Datei zu gewähren, anstatt den Zugriff für einen Ordner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b5397-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="b5397-128">Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in Stammordner oder den Ordner „Programme“ zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="b5397-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5397-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5397-129">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="b5397-130">RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b5397-130">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="b5397-131">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="b5397-131">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
