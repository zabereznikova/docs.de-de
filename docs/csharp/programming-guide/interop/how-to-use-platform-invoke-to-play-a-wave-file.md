---
title: 'Gewusst wie: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei (C#-Programmierhandbuch) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
caps.latest.revision: 30
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 67e9876bd232ec55bfb0cf8f6d8b509f8af18822
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a>Gewusst wie: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei (C#-Programmierhandbuch)
In folgendem C#-Codebeispiel wird die Verwendung von Plattformaufrufdiensten zum Abspielen einer Audiodatei im Waveformat im Windows-Betriebssystem veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispielcode wird `DllImport` verwendet, um den Einstiegspunkt der `PlaySound`-Methode von `winmm.dll` als `Form1 PlaySound()` zu importieren. Das Beispiel hat ein einfaches Windows-Formular mit einer Schaltfläche. Wenn Sie auf die Schaltfläche klicken, öffnet sich das Windows-Standarddialogfeld <xref:System.Windows.Forms.OpenFileDialog>, von wo aus Sie eine Datei zur Wiedergabe öffnen können. Wenn Sie eine Wavedatei auswählen, wird diese mit der `PlaySound()`-Methode der Assemblymethode „wimm.dll“ wiedergegeben. Weitere Informationen zur `PlaySound`-Methode von „winmm.dll“ finden Sie unter [Using the PlaySound function with Waveform-Audio Files (Verwenden der Funktion „PlaySound“ mit WAVE-Audiodateien)](http://go.microsoft.com/fwlink/?LinkId=148553). Suchen Sie nach einer Datei und wählen Sie eine aus, die über eine WAV-Erweiterung verfügt, und klicken Sie anschließend auf **Öffnen**, um die WAVE-Datei mit einem Plattformaufruf wiederzugeben. Der vollständige Pfad der ausgewählten Datei wird in einem Textfeld angezeigt.  
  
 Das Dialogfeld **Open Files** (Dateien öffnen) wird so gefiltert, dass es nur Dateien mit WAV-Erweiterung anzeigt werden. Dazu werden folgende Filtereinstellungen verwendet:  
  
 [!code-cs[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-cs[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
### <a name="to-compile-the-code"></a>Kompilieren des Codes  
  
1.  Erstellen Sie in Visual Studio ein neuen Windows-Anwendungsprojekt mit C# und nennen Sie es **WinSound**.  
  
2.  Kopieren Sie den oben stehenden Code, und fügen Sie diesen über dem Inhalt der `Form1.cs`-Datei ein.  
  
3.  Kopieren Sie folgenden Code und fügen Sie ihn in der `Form1.Designer.cs`-Datei in der `InitializeComponent()`-Methode ein, und zwar immer nach vorhandenem Code.  
  
     [!code-cs[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  Kompilieren Sie den Code, und führen Sie diesen aus.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Weitere Informationen finden Sie unter [.NET Framework-Sicherheit](http://go.microsoft.com/fwlink/?LinkId=37122).  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Überblick über die Interoperabilität](../../../csharp/programming-guide/interop/interoperability-overview.md)   
 [Überblick über die Interoperabilität](../../../csharp/programming-guide/interop/interoperability-overview.md)   
 [Genauere Betrachtung von Plattformaufrufen](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)   
 [Marshallen von Daten mit Plattformaufruf](../../../framework/interop/marshaling-data-with-platform-invoke.md)
