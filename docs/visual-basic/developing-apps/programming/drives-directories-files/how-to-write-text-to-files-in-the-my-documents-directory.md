---
title: 'Gewusst wie: Schreiben von Text in Dateien im Verzeichnis "Eigene Dateien" in Visual Basic'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, writing to
- text, writing to files
- examples [Visual Basic], text files
- writing to files, in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: c900072d184469ead75bb76a3e152edce357a34f
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="396b3-102">Gewusst wie: Schreiben von Text in Dateien im Verzeichnis "Eigene Dateien" in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="396b3-102">How to: Write Text to Files in the My Documents Directory in Visual Basic</span></span>
<span data-ttu-id="396b3-103">Mit dem `My.Computer.FileSystem.SpecialDirectories`-Objekt können Sie auf besondere Verzeichnisse zugreifen, wie z.B. das Verzeichnis **MyDocuments**.</span><span class="sxs-lookup"><span data-stu-id="396b3-103">The `My.Computer.FileSystem.SpecialDirectories` object allows you to access special directories, such as the **MyDocuments** directory.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="396b3-104">Prozedur</span><span class="sxs-lookup"><span data-stu-id="396b3-104">Procedure</span></span>  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a><span data-ttu-id="396b3-105">Schreiben von Text in Dateien im Verzeichnis „Eigene Dokumente“</span><span class="sxs-lookup"><span data-stu-id="396b3-105">To write new text files in the My Documents directory</span></span>  
  
1.  <span data-ttu-id="396b3-106">Verwenden Sie die `My.Computer.FileSystem.SpecialDirectories.MyDocuments`-Eigenschaft, um den Pfad bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="396b3-106">Use the `My.Computer.FileSystem.SpecialDirectories.MyDocuments` property to supply the path.</span></span>  
  
     <span data-ttu-id="396b3-107">[!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="396b3-107">[!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_1.vb)]</span></span>  
  
2.  <span data-ttu-id="396b3-108">Verwenden Sie die `WriteAllText`-Methode, um Text in eine angegebene Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="396b3-108">Use the `WriteAllText` method to write text to the specified file.</span></span>  
  
     <span data-ttu-id="396b3-109">[!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="396b3-109">[!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="396b3-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="396b3-110">Example</span></span>  
 <span data-ttu-id="396b3-111">[!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="396b3-111">[!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-in-the-my-documents-directory_3.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="396b3-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="396b3-112">Compiling the Code</span></span>  
 <span data-ttu-id="396b3-113">Ersetzen Sie `test.txt` durch den Namen der Datei, in die Sie schreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="396b3-113">Replace `test.txt` with the name of the file you want to write to.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="396b3-114">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="396b3-114">Robust Programming</span></span>  
 <span data-ttu-id="396b3-115">Durch diesen Code werden die Ausnahmen erneut ausgelöst, die möglicherweise beim Schreiben von Text in eine Datei auftreten.</span><span class="sxs-lookup"><span data-stu-id="396b3-115">This code rethrows all the exceptions that may occur when writing text to the file.</span></span> <span data-ttu-id="396b3-116">Sie können die Wahrscheinlichkeit des Auftretens von Ausnahmen verringern, indem Sie Steuerelemente von Windows Forms, wie z.B. die Komponenten [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) und [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) verwenden, die den Benutzer nur aus zulässigen Namen wählen lassen.</span><span class="sxs-lookup"><span data-stu-id="396b3-116">You can reduce the likelihood of exceptions by using Windows Forms controls such as the [OpenFileDialog](../../../../framework/winforms/controls/openfiledialog-component-windows-forms.md) and the [SaveFileDialog](../../../../framework/winforms/controls/savefiledialog-component-windows-forms.md) components that limit the user choices to valid file names.</span></span> <span data-ttu-id="396b3-117">Das Verwenden dieser Steuerelemente ist jedoch nicht narrensicher.</span><span class="sxs-lookup"><span data-stu-id="396b3-117">Using these controls is not foolproof, however.</span></span> <span data-ttu-id="396b3-118">Das Dateisystem kann sich zwischen dem Zeitpunkt, an dem der Benutzer eine Datei auswählt, und dem Ausführen des Codes ändern.</span><span class="sxs-lookup"><span data-stu-id="396b3-118">The file system can change between the time the user selects a file and the time that the code executes.</span></span> <span data-ttu-id="396b3-119">Das Behandeln von Ausnahmen ist deshalb beim Arbeiten mit Dateien fast immer notwendig.</span><span class="sxs-lookup"><span data-stu-id="396b3-119">Exception handling is therefore nearly always necessary when with working with files.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="396b3-120">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="396b3-120">.NET Framework Security</span></span>  
 <span data-ttu-id="396b3-121">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Code möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="396b3-121">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="396b3-122">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](https://msdn.microsoft.com/library/33tceax8).</span><span class="sxs-lookup"><span data-stu-id="396b3-122">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
 <span data-ttu-id="396b3-123">In diesem Beispiel wird eine neue Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="396b3-123">This example creates a new file.</span></span> <span data-ttu-id="396b3-124">Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine Berechtigung zum Erstellen für den Ordner.</span><span class="sxs-lookup"><span data-stu-id="396b3-124">If an application needs to create a file, that application needs Create permission for the folder.</span></span> <span data-ttu-id="396b3-125">Berechtigungen werden mithilfe von Zugriffssteuerungslisten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="396b3-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="396b3-126">Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich eine Schreibberechtigung, was einer geringeren Berechtigung entspricht.</span><span class="sxs-lookup"><span data-stu-id="396b3-126">If the file already exists, the application needs only Write permission, a lesser privilege.</span></span> <span data-ttu-id="396b3-127">Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die Leseberechtigung für eine einzelne Datei erteilt werden (anstatt Erstellberechtigungen für den gesamten Ordner zu gewähren).</span><span class="sxs-lookup"><span data-stu-id="396b3-127">Where possible, it is more secure to create the file during deployment, and only grant Read privileges to a single file, rather than to grant Create privileges for a folder.</span></span> <span data-ttu-id="396b3-128">Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in Stammordner oder den Ordner **Programme** zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="396b3-128">Also, it is more secure to write data to user folders than to the root folder or the **Program Files** folder.</span></span> <span data-ttu-id="396b3-129">Weitere Informationen finden Sie unter [Übersicht über die ACL-Technologie](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045).</span><span class="sxs-lookup"><span data-stu-id="396b3-129">For more information, see [ACL Technology Overview](http://msdn.microsoft.com/en-us/06fbf66d-6f02-4378-b863-b2f12e349045).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="396b3-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="396b3-130">See Also</span></span>  
 <xref:System.IO.Path.Combine%2A?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>

