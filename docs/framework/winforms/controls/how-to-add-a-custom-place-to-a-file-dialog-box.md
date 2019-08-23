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
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a>Vorgehensweise: Hinzufügen eines benutzerdefinierten Speicherorts zum Dialogfeld „Datei“
In [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] befindet sich in den Standarddialogfeldern zum Öffnen und Schließen auf der linken Seite ein Bereich mit der Bezeichnung **Linkfavoriten**. Dieser Bereich wird als „Benutzerdefinierte Speicherorte“ bezeichnet. Mit <xref:System.Windows.Forms.OpenFileDialog> der <xref:System.Windows.Forms.SaveFileDialog> -Klasse und der-Klasse können Sie <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> der Auflistung Ordner hinzufügen.  
  
> [!NOTE]
> Damit ein Benutzer <xref:System.Windows.Forms.OpenFileDialog> definierter Speicherort in oder <xref:System.Windows.Forms.SaveFileDialog>angezeigt wird, muss die <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> -Eigenschaft auf `true` festgelegt werden (Standardeinstellung).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>So fügen Sie dem Dialogfeld „Datei“ einen benutzerdefinierten Speicherort hinzu  
  
- Fügen Sie der <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> -Auflistung des Dialog Felds einen Pfad, eine <xref:System.Windows.Forms.FileDialogCustomPlace> bekannte Ordner-GUID oder ein-Objekt hinzu.  
  
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
