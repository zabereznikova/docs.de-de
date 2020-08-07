---
title: 'Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateioperationen (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie mithilfe der Methode „CopyFile (String, String, UIOption)“ ein Statusdialogfeld für Dateivorgänge bereitstellen.
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: 2ea18d924b47fc10412d37479f1b09f7eef7ad3b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301969"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="d5a11-103">Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateioperationen (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="d5a11-103">How to provide a progress dialog box for file operations (C# Programming Guide)</span></span>
<span data-ttu-id="d5a11-104">Sie können ein Standarddialogfeld bereitstellen, das den Verlauf bei Dateivorgängen in Windows anzeigt, wenn Sie die Methode <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> im <xref:Microsoft.VisualBasic?displayProperty=nameWithType>-Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5a11-104">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="d5a11-105">So fügen Sie einen Verweis in Visual Studio hinzu</span><span class="sxs-lookup"><span data-stu-id="d5a11-105">To add a reference in Visual Studio</span></span>  
  
1. <span data-ttu-id="d5a11-106">Wählen Sie in der Menüleiste die Optionen **Projekt** und **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d5a11-106">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="d5a11-107">Das Dialogfeld **Verweis-Manager** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d5a11-107">The **Reference Manager** dialog box appears.</span></span>  
  
2. <span data-ttu-id="d5a11-108">Wählen Sie im Bereich **Assemblys** die Option **Framework** aus, wenn sie nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d5a11-108">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
3. <span data-ttu-id="d5a11-109">Aktivieren Sie in der Namensliste das Kontrollkästchen **Microsoft.VisualBasic**, und schließen Sie dann das Dialogfeld durch Auswählen der Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5a11-109">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5a11-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d5a11-110">Example</span></span>  
 <span data-ttu-id="d5a11-111">Im folgenden Code wird das von `sourcePath` angegebene Verzeichnis in das von `destinationPath` angegebene Verzeichnis kopiert.</span><span class="sxs-lookup"><span data-stu-id="d5a11-111">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="d5a11-112">Mit diesem Code wird auch ein Standarddialogfeld bereitgestellt, in dem die geschätzte Zeit angezeigt wird, die bis zum Abschluss des Vorgangs verbleibt.</span><span class="sxs-lookup"><span data-stu-id="d5a11-112">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 [!code-csharp[csFilesandFolders#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="d5a11-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5a11-113">See also</span></span>

- [<span data-ttu-id="d5a11-114">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d5a11-114">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
