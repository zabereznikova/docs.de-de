---
title: 'Vorgehensweise: Wiedergabe eines Signaltons in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], beep
- Windows Forms, sounds
- sounds [Windows Forms], playing
- forms [Windows Forms], sounds
- examples [Windows Forms], sounds
ms.assetid: 7ea5cded-4888-4f35-8f28-5cab1a55c973
ms.openlocfilehash: d04bf4bd45aa6ba5dfe231d5f69c2b2a13765373
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710432"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a>Vorgehensweise: Wiedergabe eines Signaltons in Windows Forms
In diesem Beispiel wird einen Signalton zur Laufzeit wiedergegeben.  
  
## <a name="example"></a>Beispiel  
  
```vb  
Public Sub OnePing()  
    Beep()  
End Sub  
```  
  
```csharp  
public void onePing()  
{  
    SystemSounds.Beep.Play();  
}  
```  
  
> [!NOTE]
>  Der Sound wiedergegeben, der C# Codebeispiel richtet sich nach der <xref:System.Media.SystemSounds.Beep%2A> sound Systemeinstellung. Weitere Informationen finden Sie unter <xref:System.Media.SystemSounds>.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für C#, in diesem Beispiel erfordert einen Verweis auf die <xref:System.Media?displayProperty=nameWithType> Namespace.  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [Vorgehensweise: Wiedergabe eines Systemsounds in Windows Forms](how-to-play-a-system-sound-from-a-windows-form.md)
- [Vorgehensweise: Wiedergabe von Sound in Windows Forms](how-to-play-a-sound-from-a-windows-form.md)
