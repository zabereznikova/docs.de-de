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
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Gewusst wie: Hinzufügen eines benutzerdefinierten Speicherorts zum Dialogfeld "Datei"
In [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] befindet sich in den Standarddialogfeldern zum Öffnen und Schließen auf der linken Seite ein Bereich mit der Bezeichnung **Linkfavoriten**. Dieser Bereich wird als „Benutzerdefinierte Speicherorte“ bezeichnet. Die <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> Klassen ermöglichen Ihnen das Hinzufügen von Ordnern auf dem <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> Auflistung.  
  
> [!NOTE]
>  In der Reihenfolge für einen benutzerdefinierten Speicherort im angezeigt werden die <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> Eigenschaft muss festgelegt werden, um `true` (Standard).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>So fügen Sie dem Dialogfeld „Datei“ einen benutzerdefinierten Speicherort hinzu  
  
-   Fügen Sie einen Pfad, eine bekannte Ordner-GUID oder eine <xref:System.Windows.Forms.FileDialogCustomPlace> -Objekt an die <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> Auflistung des Dialogfelds.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Pfad hinzufügen:  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.FileDialog>  
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>  
 [GUIDs von bekannten Ordnern für benutzerdefinierte Speicherorte im Dateidialogfeld](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)
