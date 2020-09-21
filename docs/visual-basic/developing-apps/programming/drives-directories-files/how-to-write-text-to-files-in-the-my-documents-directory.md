---
title: 'Gewusst wie: Schreiben von Text in Dateien im Verzeichnis "Eigene Dateien"'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- examples [Visual Basic], text files
- writing to files [Visual Basic], in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
ms.openlocfilehash: bb3a9bdc44f86fbcdb3c56ee088740efdfebe95d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546457"
---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a><span data-ttu-id="c7b0f-102">Gewusst wie: Schreiben von Text in Dateien im Verzeichnis "Eigene Dateien" in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7b0f-102">How to: Write Text to Files in the My Documents Directory in Visual Basic</span></span>

<span data-ttu-id="c7b0f-103">Mit dem `My.Computer.FileSystem.SpecialDirectories`-Objekt können Sie auf besondere Verzeichnisse zugreifen, wie z.B. das Verzeichnis **MyDocuments**.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-103">The `My.Computer.FileSystem.SpecialDirectories` object allows you to access special directories, such as the **MyDocuments** directory.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="c7b0f-104">Prozedur</span><span class="sxs-lookup"><span data-stu-id="c7b0f-104">Procedure</span></span>  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a><span data-ttu-id="c7b0f-105">Schreiben von Text in Dateien im Verzeichnis „Eigene Dokumente“</span><span class="sxs-lookup"><span data-stu-id="c7b0f-105">To write new text files in the My Documents directory</span></span>  
  
1. <span data-ttu-id="c7b0f-106">Verwenden Sie die `My.Computer.FileSystem.SpecialDirectories.MyDocuments`-Eigenschaft, um den Pfad bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-106">Use the `My.Computer.FileSystem.SpecialDirectories.MyDocuments` property to supply the path.</span></span>  
  
     [!code-vb[VbFileIOWrite#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="c7b0f-107">Verwenden Sie die `WriteAllText`-Methode, um Text in eine angegebene Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-107">Use the `WriteAllText` method to write text to the specified file.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="c7b0f-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7b0f-108">Example</span></span>  

 [!code-vb[VbFileIOWrite#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7b0f-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c7b0f-109">Compiling the Code</span></span>  

 <span data-ttu-id="c7b0f-110">Ersetzen Sie `test.txt` durch den Namen der Datei, in die Sie schreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-110">Replace `test.txt` with the name of the file you want to write to.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c7b0f-111">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="c7b0f-111">Robust Programming</span></span>  

 <span data-ttu-id="c7b0f-112">Durch diesen Code werden die Ausnahmen erneut ausgelöst, die möglicherweise beim Schreiben von Text in eine Datei auftreten.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-112">This code rethrows all the exceptions that may occur when writing text to the file.</span></span> <span data-ttu-id="c7b0f-113">Sie können die Wahrscheinlichkeit des Auftretens von Ausnahmen verringern, indem Sie Steuerelemente von Windows Forms, wie z.B. die Komponenten [OpenFileDialog](/dotnet/desktop/winforms/controls/openfiledialog-component-windows-forms) und [SaveFileDialog](/dotnet/desktop/winforms/controls/savefiledialog-component-windows-forms) verwenden, die den Benutzer nur aus zulässigen Namen wählen lassen.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-113">You can reduce the likelihood of exceptions by using Windows Forms controls such as the [OpenFileDialog](/dotnet/desktop/winforms/controls/openfiledialog-component-windows-forms) and the [SaveFileDialog](/dotnet/desktop/winforms/controls/savefiledialog-component-windows-forms) components that limit the user choices to valid file names.</span></span> <span data-ttu-id="c7b0f-114">Das Verwenden dieser Steuerelemente ist jedoch nicht narrensicher.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-114">Using these controls is not foolproof, however.</span></span> <span data-ttu-id="c7b0f-115">Das Dateisystem kann sich zwischen dem Zeitpunkt, an dem der Benutzer eine Datei auswählt, und dem Ausführen des Codes ändern.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-115">The file system can change between the time the user selects a file and the time that the code executes.</span></span> <span data-ttu-id="c7b0f-116">Das Behandeln von Ausnahmen ist deshalb beim Arbeiten mit Dateien fast immer notwendig.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-116">Exception handling is therefore nearly always necessary when with working with files.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c7b0f-117">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c7b0f-117">.NET Framework Security</span></span>  

 <span data-ttu-id="c7b0f-118">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Code möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-118">If you are running in a partial-trust context, the code might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="c7b0f-119">Weitere Informationen finden Sie unter [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="c7b0f-119">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
 <span data-ttu-id="c7b0f-120">In diesem Beispiel wird eine neue Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-120">This example creates a new file.</span></span> <span data-ttu-id="c7b0f-121">Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine Berechtigung zum Erstellen für den Ordner.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-121">If an application needs to create a file, that application needs Create permission for the folder.</span></span> <span data-ttu-id="c7b0f-122">Berechtigungen werden mithilfe von Zugriffssteuerungslisten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-122">Permissions are set using access control lists.</span></span> <span data-ttu-id="c7b0f-123">Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich eine Schreibberechtigung, was einer geringeren Berechtigung entspricht.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-123">If the file already exists, the application needs only Write permission, a lesser privilege.</span></span> <span data-ttu-id="c7b0f-124">Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die Leseberechtigung für eine einzelne Datei erteilt werden (anstatt Erstellberechtigungen für den gesamten Ordner zu gewähren).</span><span class="sxs-lookup"><span data-stu-id="c7b0f-124">Where possible, it is more secure to create the file during deployment, and only grant Read privileges to a single file, rather than to grant Create privileges for a folder.</span></span> <span data-ttu-id="c7b0f-125">Darüber hinaus ist es sicherer, Daten in Benutzerordner statt in Stammordner oder den Ordner **Programme** zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="c7b0f-125">Also, it is more secure to write data to user folders than to the root folder or the **Program Files** folder.</span></span> <span data-ttu-id="c7b0f-126">Weitere Informationen finden Sie unter [Übersicht über die ACL-Technologie](/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c7b0f-126">For more information, see [ACL Technology Overview](/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b0f-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7b0f-127">See also</span></span>

- <xref:System.IO.Path.Combine%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
