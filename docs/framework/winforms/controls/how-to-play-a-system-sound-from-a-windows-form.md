---
title: 'Vorgehensweise: Wiedergabe eines Systemsounds in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing for system events
- playing sounds [Windows Forms], Windows Forms
- system sounds [Windows Forms], playing from Windows Forms
- playing sounds [Windows Forms], system
- SoundPlayer class [Windows Forms], system sounds
- sounds [Windows Forms], playing
- examples [Windows Forms], sounds
ms.assetid: afb206ff-4824-4804-a8d4-185bf5ad8e7c
ms.openlocfilehash: 1883e73f3b1937e8568b751d1cb9f3b57548c010
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649504"
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a>Vorgehensweise: Wiedergabe eines Systemsounds in Windows Forms
Im folgenden Codebeispiel wird der Systemsound `Exclamation` zur Laufzeit wiedergegeben. Weitere Informationen zu Systemsounds finden Sie unter <xref:System.Media.SystemSounds>.  
  
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
  
-   Einen Verweis auf den <xref:System.Media?displayProperty=nameWithType>-Namespace  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
- [Vorgehensweise: Wiedergabe eines Signaltons in Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-beep-from-a-windows-form.md)
- [Vorgehensweise: Wiedergabe von Sound in Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
