---
title: 'Gewusst wie: Wiedergabe eines Signaltons in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0c0c369756547231c0f8171bdfa940cb353544b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a>Gewusst wie: Wiedergabe eines Signaltons in Windows Forms
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
>  Der Sound wiedergegeben, in der C#-Codebeispiel richtet sich nach der <xref:System.Media.SystemSounds.Beep%2A> sound Systemeinstellung. Weitere Informationen finden Sie unter <xref:System.Media.SystemSounds>.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für c#, dieses Beispiel benötigen Sie einen Verweis auf die <xref:System.Media?displayProperty=nameWithType> Namespace.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.Beep%2A>  
 <xref:System.Media.SoundPlayer>  
 [Gewusst wie: Wiedergabe eines Systemsounds in Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-system-sound-from-a-windows-form.md)  
 [Gewusst wie: Wiedergabe von Sound in Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
