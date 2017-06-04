---
title: "Gewusst wie: Hinzuf&#252;gen eines gemeinsamen Orts zum Dialogfeld &quot;Datei&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Gemeinsamer Ort zu einem Dialogfeld"
  - "Hinzufügen eines gemeinsamen Orts zu einem Dialogfeld"
  - "CustomPlaces-Auflistung"
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Hinzuf&#252;gen eines gemeinsamen Orts zum Dialogfeld &quot;Datei&quot;
Das Öffnen und Schließen von Dialogfeldern auf [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] haben einen Bereich auf der linken Seite des Dialogfelds mit der Bezeichnung **Favoriten**. Dieser Bereich wird die benutzerdefinierte Speicherorte bezeichnet. Die <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> Klassen können Sie Ordner zum Hinzufügen der <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> Auflistung.  
  
> [!NOTE]
>  In der Reihenfolge für einen benutzerdefinierten Speicherort angezeigt werden die <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> Eigenschaft muss festgelegt werden, um `true` (Standard).  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a>Um einen benutzerdefinierten Speicherort im Dialogfeld Datei hinzufügen  
  
-   Fügen Sie einen Pfad, eine GUID für bekannte Ordner oder ein <xref:System.Windows.Forms.FileDialogCustomPlace> -Objekt an die <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> Auflistung des Dialogfelds.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie einen Pfad hinzugefügt wird:  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.FileDialog>   
 <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=fullName>   
 [GUIDs von bekannten Ordnern für benutzerdefinierte Speicherorte im Dateidialogfeld](../../../../docs/framework/winforms/controls/known-folder-guids-for-file-dialog-custom-places.md)