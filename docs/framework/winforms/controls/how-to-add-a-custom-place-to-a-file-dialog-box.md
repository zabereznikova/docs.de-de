---
title: 'Gewusst wie: Hinzufügen eines benutzerdefinierten Speicherorts zum Dialogfeld "Datei"'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 7172e484451cf932413920910ec9124b3388bd76
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976992"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="c10a9-102">Gewusst wie: Hinzufügen eines benutzerdefinierten Speicherorts zum Dialogfeld "Datei"</span><span class="sxs-lookup"><span data-stu-id="c10a9-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="c10a9-103">Die Standard Dialogfelder zum Öffnen und speichern in Windows Vista haben einen Bereich auf der linken Seite des Dialog Felds mit der Bezeichnung **Favoriten Links**.</span><span class="sxs-lookup"><span data-stu-id="c10a9-103">The default open and save dialog boxes on Windows Vista have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="c10a9-104">Dieser Bereich wird als „Benutzerdefinierte Speicherorte“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c10a9-104">This area is called custom places.</span></span> <span data-ttu-id="c10a9-105">Die Klassen <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> ermöglichen es Ihnen, der <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> Auflistung Ordner hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c10a9-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c10a9-106">Damit ein benutzerdefinierter Speicherort im <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog>angezeigt wird, muss die Eigenschaft <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> auf `true` (Standardeinstellung) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c10a9-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="c10a9-107">So fügen Sie dem Dialogfeld „Datei“ einen benutzerdefinierten Speicherort hinzu</span><span class="sxs-lookup"><span data-stu-id="c10a9-107">To add a custom place to a file dialog box</span></span>  
  
- <span data-ttu-id="c10a9-108">Fügen Sie der <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>-Auflistung des Dialog Felds einen Pfad, eine GUID für einen bekannten Ordner oder ein <xref:System.Windows.Forms.FileDialogCustomPlace> Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="c10a9-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="c10a9-109">Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Pfad hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="c10a9-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c10a9-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c10a9-110">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c10a9-111">GUIDs von bekannten Ordnern für benutzerdefinierte Speicherorte im Dateidialogfeld</span><span class="sxs-lookup"><span data-stu-id="c10a9-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](known-folder-guids-for-file-dialog-custom-places.md)
