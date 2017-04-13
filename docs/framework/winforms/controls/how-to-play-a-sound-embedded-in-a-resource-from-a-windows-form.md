---
title: "Gewusst wie: Wiedergeben eines in einer Ressource aus Windows Form eingebetteten Sounds | Microsoft Docs"
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
  - "Sounds, Wiedergabe aus Ressourcen"
  - "Ressourcen [Windows Forms], Wiedergabe von Tönen"
  - "Wiedergabe von Tönen, von Ressourcen"
  - "SoundPlayer-Klasse, die Wiedergabe von Tönen aus Ressourcen"
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Wiedergeben eines in einer Ressource aus Windows Form eingebetteten Sounds
Sie können die <xref:System.Media.SoundPlayer> Klasse zum Abspielen eines Sounds aus einer eingebetteten Ressource.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.Sound#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
 Importieren der <xref:System.Media?displayProperty=fullName> Namespace.  
  
 Die Sounddatei als eingebettete Ressource in Ihrem Projekt.  
  
 Ersetzen Sie dabei "<>\>" durch den Namen der Assembly in die Datei eingebettet ist. Schließen Sie nicht das Suffix ".dll".  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Media.SoundPlayer>   
 [Gewusst wie: Wiedergabe von Sound in Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)   
 [Gewusst wie: Schleife ein wiedergegebenen Sounds in einem Windows Form](../../../../docs/framework/winforms/controls/how-to-loop-a-sound-playing-on-a-windows-form.md)