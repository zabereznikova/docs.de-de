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
ms.openlocfilehash: 7a6ace385f7594a467785fbc677517c8a6e1ab53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525738"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="c4fa1-102">Gewusst wie: Hinzufügen eines benutzerdefinierten Speicherorts zum Dialogfeld "Datei"</span><span class="sxs-lookup"><span data-stu-id="c4fa1-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="c4fa1-103">In [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] befindet sich in den Standarddialogfeldern zum Öffnen und Schließen auf der linken Seite ein Bereich mit der Bezeichnung **Linkfavoriten**.</span><span class="sxs-lookup"><span data-stu-id="c4fa1-103">The default open and save dialog boxes on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="c4fa1-104">Dieser Bereich wird als „Benutzerdefinierte Speicherorte“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c4fa1-104">This area is called custom places.</span></span> <span data-ttu-id="c4fa1-105">Die <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> Klassen ermöglichen Ihnen das Hinzufügen von Ordnern auf dem <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="c4fa1-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4fa1-106">In der Reihenfolge für einen benutzerdefinierten Speicherort im angezeigt werden die <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> Eigenschaft muss festgelegt werden, um `true` (Standard).</span><span class="sxs-lookup"><span data-stu-id="c4fa1-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="c4fa1-107">So fügen Sie dem Dialogfeld „Datei“ einen benutzerdefinierten Speicherort hinzu</span><span class="sxs-lookup"><span data-stu-id="c4fa1-107">To add a custom place to a file dialog box</span></span>  
  
-   <span data-ttu-id="c4fa1-108">Fügen Sie einen Pfad, eine bekannte Ordner-GUID oder eine <xref:System.Windows.Forms.FileDialogCustomPlace> -Objekt an die <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> Auflistung des Dialogfelds.</span><span class="sxs-lookup"><span data-stu-id="c4fa1-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="c4fa1-109">Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Pfad hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="c4fa1-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c4fa1-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4fa1-110">See Also</span></span>  
 <xref:System.Windows.Forms.FileDialog>  
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="c4fa1-111">GUIDs von bekannten Ordnern für benutzerdefinierte Speicherorte im Dateidialogfeld</span><span class="sxs-lookup"><span data-stu-id="c4fa1-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)
