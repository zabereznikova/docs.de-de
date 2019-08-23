---
title: 'Vorgehensweise: Hinzufügen eines benutzerdefinierten Speicherorts zum Dialogfeld „Datei“'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 824c948fafd0a0995ad261389414d2d79918c8a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916349"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="c3a5b-102">Vorgehensweise: Hinzufügen eines benutzerdefinierten Speicherorts zum Dialogfeld „Datei“</span><span class="sxs-lookup"><span data-stu-id="c3a5b-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="c3a5b-103">In [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] befindet sich in den Standarddialogfeldern zum Öffnen und Schließen auf der linken Seite ein Bereich mit der Bezeichnung **Linkfavoriten**.</span><span class="sxs-lookup"><span data-stu-id="c3a5b-103">The default open and save dialog boxes on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="c3a5b-104">Dieser Bereich wird als „Benutzerdefinierte Speicherorte“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c3a5b-104">This area is called custom places.</span></span> <span data-ttu-id="c3a5b-105">Mit <xref:System.Windows.Forms.OpenFileDialog> der <xref:System.Windows.Forms.SaveFileDialog> -Klasse und der-Klasse können Sie <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> der Auflistung Ordner hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c3a5b-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c3a5b-106">Damit ein Benutzer <xref:System.Windows.Forms.OpenFileDialog> definierter Speicherort in oder <xref:System.Windows.Forms.SaveFileDialog>angezeigt wird, muss die <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> -Eigenschaft auf `true` festgelegt werden (Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="c3a5b-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="c3a5b-107">So fügen Sie dem Dialogfeld „Datei“ einen benutzerdefinierten Speicherort hinzu</span><span class="sxs-lookup"><span data-stu-id="c3a5b-107">To add a custom place to a file dialog box</span></span>  
  
- <span data-ttu-id="c3a5b-108">Fügen Sie der <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> -Auflistung des Dialog Felds einen Pfad, eine <xref:System.Windows.Forms.FileDialogCustomPlace> bekannte Ordner-GUID oder ein-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="c3a5b-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="c3a5b-109">Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Pfad hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="c3a5b-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c3a5b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3a5b-110">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c3a5b-111">GUIDs von bekannten Ordnern für benutzerdefinierte Speicherorte im Dateidialogfeld</span><span class="sxs-lookup"><span data-stu-id="c3a5b-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](known-folder-guids-for-file-dialog-custom-places.md)
