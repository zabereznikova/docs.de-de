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
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Gewusst wie: Hinzufügen eines benutzerdefinierten Speicherorts zum Dialogfeld "Datei"
Die Standard Dialogfelder zum Öffnen und speichern in Windows Vista haben einen Bereich auf der linken Seite des Dialog Felds mit der Bezeichnung **Favoriten Links**. Dieser Bereich wird als „Benutzerdefinierte Speicherorte“ bezeichnet. Die Klassen <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> ermöglichen es Ihnen, der <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> Auflistung Ordner hinzuzufügen.  
  
> [!NOTE]
> Damit ein benutzerdefinierter Speicherort im <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog>angezeigt wird, muss die Eigenschaft <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> auf `true` (Standardeinstellung) festgelegt werden.  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>So fügen Sie dem Dialogfeld „Datei“ einen benutzerdefinierten Speicherort hinzu  
  
- Fügen Sie der <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A>-Auflistung des Dialog Felds einen Pfad, eine GUID für einen bekannten Ordner oder ein <xref:System.Windows.Forms.FileDialogCustomPlace> Objekt hinzu.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Pfad hinzufügen:  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [GUIDs von bekannten Ordnern für benutzerdefinierte Speicherorte im Dateidialogfeld](known-folder-guids-for-file-dialog-custom-places.md)
