---
title: "Gewusst wie: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "WAV-Dateien"
  - "Interoperabilität [C#], Wiedergeben von WAV-Dateien per pinvoke"
  - "Plattformaufruf, Audiodateien"
  - "WAV-Dateien"
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
caps.latest.revision: 30
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 30
---
# Gewusst wie: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei (C#-Programmierhandbuch)
Das folgende C\#\-Codebeispiel veranschaulicht die Verwendung von Plattformaufrufdiensten zum Wiedergeben einer Wavedatei in Windows.  
  
## Beispiel  
 In diesem Beispielcode wird `DllImport` verwendet, um den Einstiegspunkt der `PlaySound`\-Methode von `winmm.dll` als `Form1 PlaySound()` zu importieren.  Das Beispiel verfügt über ein einfaches Windows Form mit einer Schaltfläche.  Durch Klicken auf die Schaltfläche wird das Windows\-Standarddialogfeld <xref:System.Windows.Forms.OpenFileDialog> geöffnet, mit dem Sie die Datei öffnen können, die wiedergegeben werden soll.  Die ausgewählte Wavedatei wird dann mit der `PlaySound()`\-Methode der winmm.DLL\-Assemblymethode wiedergegeben.  Weitere Informationen zur `PlaySound`\-Methode von winmm.dll finden Sie unter [Using the PlaySound function with Waveform\-Audio Files](http://go.microsoft.com/fwlink/?LinkId=148553).  Navigieren Sie zu einer WAV\-Datei, und wählen Sie sie aus. Klicken Sie anschließend auf **Öffnen**, um die Wavedatei unter Verwendung des Plattformaufrufs wiederzugeben.  Der vollständige Pfad der ausgewählten Datei wird in einem Textfeld angezeigt.  
  
 Im Dialogfeld **Geöffnete Dateien** wird ein Filter angewendet, sodass nur Dateien mit der Erweiterung .wav angezeigt werden:  
  
 [!code-cs[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-cs[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## Kompilieren des Codes  
  
### So kompilieren Sie den Code  
  
1.  Erstellen Sie in Visual Studio ein neues C\#\-Windows\-Anwendungsprojekt, und nennen Sie es WinSound.  
  
2.  Kopieren Sie den obigen Code, und fügen Sie ihn statt des bisherigen Inhalts in die Datei `Form1.cs` ein.  
  
3.  Kopieren Sie den folgenden Code, und fügen Sie ihn in die Datei `Form1.Designer.cs` in der `InitializeComponent()`\-Methode nach dem vorhandenen Code ein.  
  
     [!code-cs[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  Kompilieren Sie den Code, und führen Sie ihn aus.  
  
## .NET Framework-Sicherheit  
 Informationen finden Sie unter [.NET Framework Security](http://go.microsoft.com/fwlink/?LinkId=37122).  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Überblick über die Interoperabilität](../../../csharp/programming-guide/interop/interoperability-overview.md)   
 [Überblick über die Interoperabilität](../../../csharp/programming-guide/interop/interoperability-overview.md)   
 [A Closer Look at Platform Invoke](http://msdn.microsoft.com/de-de/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)   
 [Marshaling Data with Platform Invoke](../Topic/Marshaling%20Data%20with%20Platform%20Invoke.md)