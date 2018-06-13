---
title: 'Gewusst wie: Wiedergabe eines Systemsounds in Windows Forms'
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
ms.openlocfilehash: 4dfda2b6d73e346d85690f66a3e92858381ae7af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532398"
---
# <a name="how-to-play-a-system-sound-from-a-windows-form"></a>Gewusst wie: Wiedergabe eines Systemsounds in Windows Forms
Im folgenden Codebeispiel wird der Systemsound `Exclamation` zur Laufzeit wiedergegeben. Weitere Informationen zu Systemsounds wiederzugeben, finden Sie unter <xref:System.Media.SystemSounds>.  
  
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
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>  
 [Gewusst wie: Wiedergabe eines Signaltons in Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-beep-from-a-windows-form.md)  
 [Gewusst wie: Wiedergabe von Sound in Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
