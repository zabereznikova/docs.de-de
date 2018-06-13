---
title: 'Gewusst wie: Wiedergeben eines in einer Ressource aus Windows Form eingebetteten Sounds'
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
ms.openlocfilehash: c9dc8499e2d12ed17f9b409a805148d08da894fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532134"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a>Gewusst wie: Wiedergeben eines in einer Ressource aus Windows Form eingebetteten Sounds
Sie können die <xref:System.Media.SoundPlayer> -Klasse zum Abspielen eines Sounds aus einer eingebetteten Ressource.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
 Importieren der <xref:System.Media?displayProperty=nameWithType> Namespace.  
  
 Die Sounddatei wird als eingebettete Ressource in das Projekt aufgenommen.  
  
 „\<AssemblyName>“ wird durch den Namen der Assembly ersetzt, in die die Sounddatei eingebettet ist. Das Suffix „.dll“ wird nicht angegeben.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Media.SoundPlayer>  
 [Gewusst wie: Wiedergabe von Sound in Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)  
 [Gewusst wie: Starten einer Schleife eines wiedergegebenen Sounds in Windows Form](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)
