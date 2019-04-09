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
ms.openlocfilehash: a646d9b04bbe824d093b106f5cfcb0f1703c6e21
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213531"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="338e5-102">Vorgehensweise: Speichern von Dateien mit dem RichTextBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="338e5-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="338e5-103">Die Windows-Formulare <xref:System.Windows.Forms.RichTextBox> Steuerelement kann schreiben, die Informationen, die in verschiedenen Formaten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="338e5-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>  
  
-   <span data-ttu-id="338e5-104">Nur-Text</span><span class="sxs-lookup"><span data-stu-id="338e5-104">Plain text</span></span>  
  
-   <span data-ttu-id="338e5-105">Unicode-nur-text</span><span class="sxs-lookup"><span data-stu-id="338e5-105">Unicode plain text</span></span>  
  
-   <span data-ttu-id="338e5-106">Rich-Text-Format (RTF)</span><span class="sxs-lookup"><span data-stu-id="338e5-106">Rich-Text Format (RTF)</span></span>  
  
-   <span data-ttu-id="338e5-107">RTF mit Leerzeichen anstelle von OLE-Objekte</span><span class="sxs-lookup"><span data-stu-id="338e5-107">RTF with spaces in place of OLE objects</span></span>  
  
-   <span data-ttu-id="338e5-108">Nur-Text mit einer Textdarstellung von OLE-Objekten</span><span class="sxs-lookup"><span data-stu-id="338e5-108">Plain text with a textual representation of OLE objects</span></span>  
  
 <span data-ttu-id="338e5-109">Um eine Datei zu speichern, rufen die <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="338e5-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="338e5-110">Sie können auch die **SaveFile** Methode zum Speichern von Daten in einen Stream.</span><span class="sxs-lookup"><span data-stu-id="338e5-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="338e5-111">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="338e5-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="338e5-112">Um den Inhalt des Steuerelements in einer Datei speichern</span><span class="sxs-lookup"><span data-stu-id="338e5-112">To save the contents of the control to a file</span></span>  
  
1.  <span data-ttu-id="338e5-113">Bestimmen Sie den Pfad der Datei gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="338e5-113">Determine the path of the file to be saved.</span></span>  
  
     <span data-ttu-id="338e5-114">Zu diesem Zweck in einer echten Anwendung würden Sie normalerweise verwenden die <xref:System.Windows.Forms.SaveFileDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="338e5-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="338e5-115">Eine Übersicht finden Sie unter [Übersicht über die SaveFileDialog-Komponente](savefiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="338e5-115">For an overview, see [SaveFileDialog Component Overview](savefiledialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="338e5-116">Rufen Sie die <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> -Methode der der <xref:System.Windows.Forms.RichTextBox> Steuerelement, zu speichernden Datei und optional einen Dateityp angeben.</span><span class="sxs-lookup"><span data-stu-id="338e5-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="338e5-117">Wenn Sie die Methode mit einem Dateinamen als einziges Argument aufrufen, wird die Datei im RTF-Format gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="338e5-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="338e5-118">Rufen Sie zum Angeben eines anderen Dateityps die Methode mit dem Wert der <xref:System.Windows.Forms.RichTextBoxStreamType> -Enumeration als zweites Argument auf.</span><span class="sxs-lookup"><span data-stu-id="338e5-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>  
  
     <span data-ttu-id="338e5-119">Im folgenden Beispiel wird der Pfad festgelegt, für der Speicherort der RTF Datei ist die **eigene** Ordner.</span><span class="sxs-lookup"><span data-stu-id="338e5-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="338e5-120">Dieser Speicherort wird verwendet, da Sie davon ausgehen können, dass dieser Ordner die meisten Computer, die das Windows-Betriebssystem ausgeführt wird enthält.</span><span class="sxs-lookup"><span data-stu-id="338e5-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="338e5-121">Dieser Speicherort kann auch Benutzer mit minimalen Systemzugriffsebenen die Anwendung sicher ausführen.</span><span class="sxs-lookup"><span data-stu-id="338e5-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="338e5-122">Im folgenden Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.RichTextBox> Steuerelement bereits hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="338e5-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>  
  
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
    >  <span data-ttu-id="338e5-123">Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="338e5-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="338e5-124">Wenn eine Anwendung eine Datei zu erstellen muss, benötigt die Anwendung erstellen-Zugriff für den Ordner an.</span><span class="sxs-lookup"><span data-stu-id="338e5-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="338e5-125">Berechtigungen werden mithilfe von Zugriffssteuerungslisten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="338e5-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="338e5-126">Wenn die Datei bereits vorhanden ist, benötigt die Anwendung nur Schreibzugriff auf, einer geringeren Berechtigung entspricht.</span><span class="sxs-lookup"><span data-stu-id="338e5-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="338e5-127">Wenn möglich, ist es sicherer, erstellen Sie die Datei während der Bereitstellung, und nur Lesezugriff auf eine einzelne Datei, anstatt den Zugriff für einen Ordner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="338e5-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="338e5-128">Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in Stammordner oder den Ordner „Programme“ zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="338e5-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="338e5-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="338e5-129">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="338e5-130">RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="338e5-130">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="338e5-131">Steuerelemente für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="338e5-131">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
