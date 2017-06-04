---
title: "Gewusst wie: Wiedergabe eines Systemsounds in Windows Forms | Microsoft Docs"
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
  - "Sounds, Wiedergabe für Systemereignisse"
  - "Wiedergabe von Tönen, Windows Forms"
  - "Systemsounds wiederzugeben, Wiedergabe aus Windows Forms"
  - "Wiedergabe von Tönen, system"
  - "Systemsounds SoundPlayer-Klasse"
  - "Wiedergabe von Sounds"
  - "Beispiele [Windows Forms], sounds"
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Gewusst wie: Wiedergabe eines Systemsounds in Windows Forms
Im folgenden Codebeispiel wird der Wiedergabe der `Exclamation` Systemsounds zur Laufzeit. Weitere Informationen zu Systemsounds finden Sie unter <xref:System.Media.SystemSounds>.  
  
## <a name="example"></a>Beispiel  
  
```vb  
Public Sub PlayExclamation()  
    SystemSounds.Exclamation.Play()  
End Sub  
  
```  
  
```csharp  
public void playExclamation()  
{  
    SystemSounds.Exclamation.Play();  
}  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein Verweis auf die <xref:System.Media?displayProperty=fullName> Namespace.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Media.SoundPlayer>   
 <xref:System.Media.SystemSounds>   
 [Gewusst wie: Wiedergabe eines Signaltons in Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-beep-from-a-windows-form.md)   
 [Gewusst wie: Wiedergabe von Sound in Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)