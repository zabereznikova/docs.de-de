---
title: "Gewusst wie: Starten einer Schleife eines wiedergegebenen Sounds in Windows Form | Microsoft Docs"
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
  - "Wiedergabe von Tönen, Durchlaufen"
  - "Soundschleifen"
  - "SoundPlayer-Klasse, Wiedergabe von Schleifen"
  - "Sounds, Durchlaufen"
ms.assetid: ea95dd46-10a3-46c0-8263-4b205f00df7f
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Gewusst wie: Starten einer Schleife eines wiedergegebenen Sounds in Windows Form
Im folgenden Codebeispiel wird ein Sound mehrfach wiedergegeben.  Wenn der Code im `stopPlayingButton_Click`\-Ereignishandler ausgeführt wird, werden alle aktuell wiedergegebenen Sounds beendet.  Wenn kein Sound wiedergegeben wird, passiert nichts.  
  
## Beispiel  
 [!code-csharp[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.PlayLooping#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.PlayLooping/VB/Form1.vb#1)]  
  
## Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
-   Ersetzen Sie den Dateinamen `"c:\Windows\Media\chimes.wav"` durch einen gültigen Dateinamen.  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] finden Sie unter [Erstellen von der Befehlszeile aus](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) oder [Erstellen über die Befehlszeile mit csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms\-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Robuste Programmierung  
 Dateioperationen sollten in entsprechende Ausnahmebehandlungsblöcke eingeschlossen sein.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Pfadname ist falsch formatiert.  Er enthält beispielsweise unzulässige Zeichen oder besteht nur aus Leerzeichen \(<xref:System.ArgumentException>\-Klasse\).  
  
-   Der Pfad ist schreibgeschützt \(<xref:System.IO.IOException>\-Klasse\).  
  
-   Der Pfadname ist `Nothing` \(<xref:System.ArgumentNullException>\-Klasse\).  
  
-   Der Pfadname ist zu lang \(<xref:System.IO.PathTooLongException>\-Klasse\).  
  
-   Der Pfad ist ungültig \(<xref:System.IO.DirectoryNotFoundException>\-Klasse\).  
  
-   Der Pfad besteht nur aus einem Doppelpunkt ":" \(<xref:System.NotSupportedException>\-Klasse\).  
  
## .NET Framework-Sicherheit  
 Beurteilen Sie den Inhalt der Datei nicht anhand des Dateinamens.  Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic\-Quelldatei.  Überprüfen Sie alle Eingaben, bevor Sie die Daten in der Anwendung verwenden.  
  
## Siehe auch  
 <xref:System.Media.SoundPlayer.PlayLooping%2A>   
 [Gewusst wie: Wiedergabe von Sound in Windows Forms](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)   
 [Übersicht über die SoundPlayer\-Klasse](../../../../docs/framework/winforms/controls/soundplayer-class-overview.md)