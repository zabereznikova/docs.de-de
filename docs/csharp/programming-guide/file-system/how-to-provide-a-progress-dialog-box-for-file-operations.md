---
title: 'Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateioperationen – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
ms.openlocfilehash: 028e779f3cd8a17f162a79791b0c84abae14cf44
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590050"
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="bcd9b-102">Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateioperationen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="bcd9b-102">How to: Provide a Progress Dialog Box for File Operations (C# Programming Guide)</span></span>
<span data-ttu-id="bcd9b-103">Sie können ein Standarddialogfeld bereitstellen, das den Verlauf bei Dateivorgängen in Windows anzeigt, wenn Sie die Methode <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> im <xref:Microsoft.VisualBasic?displayProperty=nameWithType>-Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="bcd9b-103">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="bcd9b-104">So fügen Sie einen Verweis in Visual Studio hinzu</span><span class="sxs-lookup"><span data-stu-id="bcd9b-104">To add a reference in Visual Studio</span></span>  
  
1. <span data-ttu-id="bcd9b-105">Wählen Sie in der Menüleiste die Optionen **Projekt** und **Verweis hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="bcd9b-105">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="bcd9b-106">Das Dialogfeld **Verweis-Manager** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bcd9b-106">The **Reference Manager** dialog box appears.</span></span>  
  
2. <span data-ttu-id="bcd9b-107">Wählen Sie im Bereich **Assemblys** die Option **Framework** aus, wenn sie nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="bcd9b-107">In the **Assemblies** area, choose **Framework** if it isn’t already chosen.</span></span>  
  
3. <span data-ttu-id="bcd9b-108">Aktivieren Sie in der Namensliste das Kontrollkästchen **Microsoft.VisualBasic**, und schließen Sie dann das Dialogfeld durch Auswählen der Schaltfläche **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcd9b-108">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcd9b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bcd9b-109">Example</span></span>  
 <span data-ttu-id="bcd9b-110">Im folgenden Code wird das von `sourcePath` angegebene Verzeichnis in das von `destinationPath` angegebene Verzeichnis kopiert.</span><span class="sxs-lookup"><span data-stu-id="bcd9b-110">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="bcd9b-111">Mit diesem Code wird auch ein Standarddialogfeld bereitgestellt, in dem die geschätzte Zeit angezeigt wird, die bis zum Abschluss des Vorgangs verbleibt.</span><span class="sxs-lookup"><span data-stu-id="bcd9b-111">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 [!code-csharp[csFilesandFolders#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="bcd9b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcd9b-112">See also</span></span>

- [<span data-ttu-id="bcd9b-113">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="bcd9b-113">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
