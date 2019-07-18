---
title: 'Vorgehensweise: Wiedergeben eines in einer Ressource aus Windows Forms eingebetteten Sounds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
ms.openlocfilehash: 49235f9cb035c5a09c26b427f855fc00e818fe1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913353"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a>Vorgehensweise: Wiedergeben eines in einer Ressource aus Windows Forms eingebetteten Sounds
Sie können die <xref:System.Media.SoundPlayer> Klasse zum Abspielen eines Sounds aus einer eingebetteten Ressource.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.Sound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
 Importieren der <xref:System.Media?displayProperty=nameWithType> Namespace.  
  
 Die Sounddatei wird als eingebettete Ressource in das Projekt aufgenommen.  
  
 „\<AssemblyName>“ wird durch den Namen der Assembly ersetzt, in die die Sounddatei eingebettet ist. Das Suffix „.dll“ wird nicht angegeben.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Media.SoundPlayer>
- [Vorgehensweise: Wiedergabe von Sound in Windows Forms](how-to-play-a-sound-from-a-windows-form.md)
- [Vorgehensweise: Schleife ein wiedergegebenen Sounds in Windows Forms](how-to-loop-a-sound-playing-on-a-windows-form.md)
