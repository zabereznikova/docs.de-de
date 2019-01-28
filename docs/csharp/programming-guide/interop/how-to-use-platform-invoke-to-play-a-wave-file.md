---
title: 'Vorgehensweise: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 94c90ed264c40c99b0c139948578c85e8c9855d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696346"
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a>Vorgehensweise: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei (C#-Programmierhandbuch)
In folgendem C#-Codebeispiel wird die Verwendung von Plattformaufrufdiensten zum Abspielen einer Audiodatei im Waveformat im Windows-Betriebssystem veranschaulicht.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispielcode wird `DllImport` verwendet, um den Einstiegspunkt der `PlaySound`-Methode von `winmm.dll` als `Form1 PlaySound()` zu importieren. Das Beispiel hat ein einfaches Windows-Formular mit einer Schaltfläche. Wenn Sie auf die Schaltfläche klicken, öffnet sich das Windows-Standarddialogfeld <xref:System.Windows.Forms.OpenFileDialog>, von wo aus Sie eine Datei zur Wiedergabe öffnen können. Wenn Sie eine Wavedatei auswählen, wird diese mit der `PlaySound()`-Methode der Bibliothek `winmm.dll` wiedergegeben. Weitere Informationen zu dieser Methode finden Sie unter [Verwenden der Funktion „PlaySound“ mit Wave-Audiodateien](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files). Suchen Sie nach einer Datei und wählen Sie eine aus, die über eine WAV-Erweiterung verfügt, und klicken Sie anschließend auf **Öffnen**, um die WAVE-Datei mit einem Plattformaufruf wiederzugeben. Der vollständige Pfad der ausgewählten Datei wird in einem Textfeld angezeigt.  
  
 Das Dialogfeld **Open Files** (Dateien öffnen) wird so gefiltert, dass es nur Dateien mit WAV-Erweiterung anzeigt werden. Dazu werden folgende Filtereinstellungen verwendet:  
  
 [!code-csharp[csProgGuideInterop#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_1.cs)]  
  
 [!code-csharp[csProgGuideInterop#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_2.cs)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
### <a name="to-compile-the-code"></a>Kompilieren des Codes  
  
1.  Erstellen Sie in Visual Studio ein neuen Windows-Anwendungsprojekt mit C# und nennen Sie es **WinSound**.  
  
2.  Kopieren Sie den oben stehenden Code, und fügen Sie diesen über dem Inhalt der `Form1.cs`-Datei ein.  
  
3.  Kopieren Sie folgenden Code und fügen Sie ihn in der `Form1.Designer.cs`-Datei in der `InitializeComponent()`-Methode ein, und zwar immer nach vorhandenem Code.  
  
     [!code-csharp[csProgGuideInterop#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-platform-invoke-to-play-a-wave-file_3.cs)]  
  
4.  Kompilieren Sie den Code, und führen Sie diesen aus.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Weitere Informationen finden Sie unter [Sicherheit in .NET](../../../standard/security/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Überblick über die Interoperabilität](../../../csharp/programming-guide/interop/interoperability-overview.md)
- [Genauere Betrachtung von Plattformaufrufen](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [Marshallen von Daten mit Plattformaufruf](../../../framework/interop/marshaling-data-with-platform-invoke.md)
