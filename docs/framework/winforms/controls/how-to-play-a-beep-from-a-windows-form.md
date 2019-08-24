---
title: 'Vorgehensweise: Wiedergabe eines Signaltons in Windows Forms'
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
ms.openlocfilehash: 7fecc5d5b7259b743926713f87d9303596803582
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015813"
---
# <a name="how-to-play-a-beep-from-a-windows-form"></a><span data-ttu-id="27381-102">Vorgehensweise: Wiedergabe eines Signaltons in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="27381-102">How to: Play a Beep from a Windows Form</span></span>
<span data-ttu-id="27381-103">In diesem Beispiel wird einen Signalton zur Laufzeit wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="27381-103">This example plays a beep at run time.</span></span>

## <a name="example"></a><span data-ttu-id="27381-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="27381-104">Example</span></span>

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
> <span data-ttu-id="27381-105">Der im C# Codebeispiel wiedergegebene Sound wird von der <xref:System.Media.SystemSounds.Beep%2A> System Sound Einstellung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="27381-105">The sound played in the C# code sample is determined by the <xref:System.Media.SystemSounds.Beep%2A> system sound setting.</span></span> <span data-ttu-id="27381-106">Weitere Informationen finden Sie unter <xref:System.Media.SystemSounds>.</span><span class="sxs-lookup"><span data-stu-id="27381-106">For more information, see <xref:System.Media.SystemSounds>.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="27381-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="27381-107">Compiling the Code</span></span>
 <span data-ttu-id="27381-108">Für C#erfordert dieses Beispiel einen Verweis auf den <xref:System.Media?displayProperty=nameWithType> -Namespace.</span><span class="sxs-lookup"><span data-stu-id="27381-108">For C#, this example requires  a reference to the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="27381-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27381-109">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Beep%2A>
- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="27381-110">Vorgehensweise: Wiedergabe eines System Sounds in Windows Form</span><span class="sxs-lookup"><span data-stu-id="27381-110">How to: Play a System Sound from a Windows Form</span></span>](how-to-play-a-system-sound-from-a-windows-form.md)
- [<span data-ttu-id="27381-111">Vorgehensweise: Abspielen eines Sounds in einem Windows Form</span><span class="sxs-lookup"><span data-stu-id="27381-111">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
