---
title: Mpgo.exe (verwaltetes, profilgesteuertes Optimierungstool)
ms.date: 03/30/2017
helpviewer_keywords:
- Mpgo.exe
- training scenarios, generating profiles with
- Managed Profile Guided Optimization Tool
- Ngen.exe
- Ngen.exe, profilers and native images
ms.assetid: f6976502-a000-4fbe-aaf5-a7aab9ce4ec2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5ab3040a246a135771c45b2639567db9ab510e3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447973"
---
# <a name="mpgoexe-managed-profile-guided-optimization-tool"></a>Mpgo.exe (verwaltetes, profilgesteuertes Optimierungstool)

Das verwaltete, profilgesteuerte Optimierungstool (Managed, Profile Guides Optimization Tool, Mpgo.exe) ist ein Befehlszeilentool, das allgemeine Endbenutzerszenarios verwendet, um die vom [Native Image Generator (Ngen.exe)](ngen-exe-native-image-generator.md) erstellten Assemblys nativer Bilder zu optimieren. Mit diesem Tool können Sie Aus- und Weiterbildungsszenarien ausführen, die Profildaten generieren. Der [Native Image Generator (Ngen.exe) ](ngen-exe-native-image-generator.md) verwendet diese Daten, um die generierten Anwendungsassemblys nativer Bilder zu optimieren. Ein Aus- und Weiterbildungsszenario ist die Testausführung einer erwarteten Nutzung Ihrer Anwendung. Mpgo.exe ist in Visual Studio Ultimate 2012 und höheren Versionen verfügbar. Ab Visual Studio 2013 können Sie Mpgo.exe auch zum Optimieren von Windows 8.x Store-Apps verwenden.  
  
Profilgesteuerte Optimierung verbessert Anwendungsstartzeit, Arbeitsspeicherauslastung (Workingsetgröße) und Durchsatz, indem Daten aus Trainingsszenarien erfasst und verwendet werden, um den Aufbau von systemeigenen Abbildern zu optimieren.  
  
Wenn Sie Leistungsprobleme bei Startzeit oder Workingsetgröße für Intermediate Language (IL)-Assemblys erkennen, empfehlen wir Ihnen zunächst die Verwendung von Ngen.exe, um Just-in-Time-Kompilierungsaufwände auszuschließen und die gemeinsame Verwendung von Code zu erleichtern. Wenn Sie weitere Verbesserungen benötigen, können Sie Mpgo.exe weiter zur Optimierung der Anwendung verwenden. Sie können die Leistungsdaten von nicht optimiertem Assemblys systemeigener Abbilder als Baseline verwenden, um die Leistungszuwächse zu ermitteln. Das Verwenden von Mpgo.exe kann möglicherweise zu kürzeren Kaltstartzeiten und einer geringeren Workingsetgröße führen. Durch Mpgo.exe werden IL-Assemblys Informationen hinzugefügt, die von Ngen.exe verwendet werden, um optimierte Assemblys von systemeigenen Abbildern zu erstellen. Weitere Informationen finden Sie im Eintrag [Improving Launch Performance for your Desktop Applications (Verbessern der Startleistung für Desktopanwendungen)](https://devblogs.microsoft.com/dotnet/improving-launch-performance-for-your-desktop-applications/) im .NET-Blog.  
  
Dieses Tool wird automatisch mit Visual Studio installiert. Wenn Sie das Tool ausführen möchten, verwenden Sie die Developer-Eingabeaufforderung für Visual Studio oder die Visual Studio-Eingabeaufforderung in Windows 7 mit Administratoranmeldeinformationen, und geben Sie Folgendes an der Eingabeaufforderung ein. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).  
  
Für Desktop-Apps:  
  
```console  
mpgo –Scenario <command> [-Import <directory>] –AssemblyList <assembly1>  <assembly2> ... -OutDir <directory> [options]  
```  
  
Für Windows 8.x Store-Apps:  
  
## <a name="syntax"></a>Syntax  
  
```console  
mpgo –Scenario <packageName> -AppID <appId> -Timeout <seconds>  
```  
  
## <a name="parameters"></a>Parameter  
 Groß-/Kleinschreibung wird für alle Argumente von Mpgo.exe ignoriert. Befehlen wird ein Bindestrich vorangestellt.  
  
> [!NOTE]
> Sie können entweder `–Scenario` oder `–Import` als erforderlichen Befehl verwenden, aber nicht beide Befehle. Es wird keiner der erforderlichen Parameter verwendet, wenn Sie die Option `–Reset` angeben.

|Erforderlicher Parameter|BESCHREIBUNG|
|------------------------|-----------------|
|`-Scenario` \<*Befehl*><br /><br /> – oder –<br /><br /> `-Scenario` \<*Paketname*><br /><br /> Oder<br /><br /> `-Import` \<*Verzeichnis*>|Für Desktop-Apps verwenden Sie `–Scenario` zum Angeben des Befehls zum Ausführen der Anwendung, die Sie optimieren möchten, einschließlich aller Befehlszeilenargumente. Verwenden Sie drei Elemente von doppelten Anführungszeichen für *Befehl*, wenn es einen Pfad angibt, der Leerzeichen enthält, z.B: `mpgo.exe -scenario """C:\My App\myapp.exe""" -assemblylist """C:\My App\myapp.exe""" -outdir "C:\optimized files"`. Verwenden Sie keine doppelten Anführungszeichen, da sie nicht ordnungsgemäß funktionieren, wenn der *Befehl* Leerzeichen enthält.<br /><br /> Oder<br /><br /> Für Windows 8.x Store-Apps verwenden Sie `–Scenario` zum Angeben des Pakets, für das Sie Profilinformationen generieren möchten. Wenn Sie den Paketanzeigenamen oder den Paketfamiliennamen anstelle des vollständigen Paketnamens angeben, wählt Mpgo.exe das Paket aus, das mit dem von Ihnen eingegebenen Namen übereinstimmt, sofern nur eine Übereinstimmung vorliegt. Wenn mehrere Pakete mit dem angegebenen Namen übereinstimmen, werden Sie von Mpgo.exe aufgefordert, ein Paket auszuwählen.<br /><br /> – oder –<br /><br /> Verwenden Sie `-Import` zum Angeben, dass Optimierungsdaten aus zuvor optimiertem Assemblys zum Optimieren der Assemblys in der `-AssemblyList` verwendet werden sollen. *Verzeichnis* gibt das Verzeichnis an, das die zuvor optimierten Dateien enthält. Die in `–AssemblyList` oder `–AssemblyListFile` angegebenen Assemblys sind die neuen Versionen der mit den Daten aus den importierten Dateien zu optimierenden Assemblys. Das Verwenden der Optimierungsdaten aus früheren Versionen der Assemblys ermöglicht Ihnen die Optimierung neuer Versionen, ohne erneute Ausführung des Szenarios.  Wenn die importierten und die neuen Assemblys jedoch erheblich unterschiedlichen Code enthalten, sind die Optimierungsdaten nicht effektiv. Die Assemblynamen, die in `–AssemblyList` oder `–AssemblyListFile` angegeben werden, müssen im Verzeichnis vorhanden sein, das durch `–Import`*verzeichnis* angegeben wird. Verwenden Sie drei Elemente von doppelten Anführungszeichen für *Verzeichnis*, wenn es einen Pfad angibt, der Leerzeichen enthält.<br /><br /> Sie müssen entweder `–Scenario` oder `–Import` angeben, jedoch nicht beide.|
|`-OutDir` \<*Verzeichnis*>|Das Verzeichnis, in dem die optimierten Assemblys gespeichert werden sollen. Wenn eine Assembly bereits im Ausgabeverzeichnisordner vorhanden ist, wird eine neue Kopie erstellt und eine Indexnummer an den Namen angefügt, beispielsweise „*assemblyname*-1.exe“. Verwenden Sie doppelte Anführungszeichen um *Verzeichnis*, wenn es einen Pfad angibt, der Leerzeichen enthält.|
|`-AssemblyList` \<*Assembly1 Assembly2 ...* ><br /><br /> – oder –<br /><br /> `-AssemblyListFile` \<*Datei*>|Eine Liste von Assemblys (einschließlich EXE- und DLL-Dateien), getrennt durch Leerzeichen, von denen Sie Profilinformationen sammeln möchten. Sie können `C:\Dir\*.dll` oder `*.dll` angeben, um alle Assemblys im festgelegten oder aktuellen Arbeitsverzeichnis auszuwählen. Weitere Informationen finden Sie im Abschnitt Hinweise.<br /><br /> – oder –<br /><br /> Eine Textdatei, die die Liste der Assemblys enthält, von denen Sie Profilinformationen sammeln möchten, muss die Assemblys zeilenweise enthalten. Verwenden Sie eine Assemblydateiliste, wenn ein Assemblyname mit einem Bindestrich (-) beginnt oder benennen die Assembly um.|
|`-AppID` \<*appId*>|Die ID der Anwendung im angegebenen Paket. Wenn Sie den Platzhalter (\*) verwenden, versucht „mpgo.exe“ die AppIDs im Paket aufzulisten und greift bei einem Fehler auf die App \<*package_family_name*>! zurück. Wenn Sie eine Zeichenfolge mit einem vorangestellten Ausrufezeichen (!) angeben, wird Mpgo.exe den Paketfamiliennamen mit dem übergebenen Argument verketten.|
|`-Timeout` \<*Sekunden*>|Die Zeitspanne, in der die Windows 8.x Store-App ausgeführt werden kann, bevor die App beendet wird.|

|Optionale Parameter|BESCHREIBUNG|
|------------------------|-----------------|
|`-64bit`|Instrumentiert die Assemblys für 64-Bit-Systeme.  Sie müssen diesen Parameter für 64-Bit-Assemblys angeben, auch wenn Ihre Assembly sich selbst als 64-Bit deklariert.|
|`-ExeConfig` \<*Dateiname*>|Gibt die Konfigurationsdatei an, die in Ihrem Szenario verwendet wird, um Versions- und Loaderinformationen bereitzustellen.|
|`-f`|Erzwingt die Aufnahme der Profildaten in eine binäre Assembly, selbst wenn diese signiert ist.  Wenn die Assembly signiert ist, muss sie erneut signiert werden, andernfalls kann die Assembly nicht geladen oder ausgeführt werden.|
|`-Reset`|Setzt die Umgebung zurück, um so sicherzustellen, dass eine abgebrochene Sitzung zur Profilerstellung keine Assemblys beeinflusst, und wird dann beendet. Die Umgebung wird standardmäßig vor und nach einer Profilerstellungssitzung zurückgesetzt.|
|`-Timeout` \<*Zeit in Sekunden*>|Gibt die Profilerstellungsdauer in Sekunden an. Verwenden Sie einen Wert, der etwas über den beobachteten Startzeiten für GUI-Anwendungen liegt. Am Ende des Timeouts werden die Profildaten erfasst, obwohl die Anwendung weiterhin ausgeführt wird. Wenn Sie diese Option nicht festlegen, wird das Erstellen eines Profils bis zum Beenden der Anwendung fortgesetzt und die Daten dann aufgezeichnet.|
|`-LeaveNativeImages`|Gibt an, dass die systemeigenen instrumentierten Abbilder nach dem Ausführen des Szenarios nicht entfernt werden sollen. Diese Option wird hauptsächlich verwendet, wenn Sie die Anwendung abrufen, die Sie für das laufende Szenario angegeben haben. Es verhindert die Neuerstellung von systemeigenen Abbildern für spätere Ausführungen von Mpgo.exe. Wenn Sie die Ausführung der Anwendung abgeschlossen haben, sind bei Angabe dieser Option möglicherweise verwaiste systemeigene Abbilder im Cache vorhanden. Führen Sie in diesem Fall „Mpgo.exe“ mit demselben Szenario und Assemblys erneut aus und verwenden Sie dabei den `–RemoveNativeImages`-Parameter, um diese systemeigenen Abbilder zu entfernen.|
|`-RemoveNativeImages`|Bereinigt eine Ausführung mit der Angabe `–LeaveNativeImages`. Wenn Sie `-RemoveNativeImages` angeben, werden von „Mpgo.exe“ alle Argumente außer `-64bit` und `–AssemblyList` ignoriert, alle instrumentierten systemeigenen Abbilder entfernt und das Programm beendet.|

## <a name="remarks"></a>Anmerkungen
 Sie können sowohl `–AssemblyList` and `- AssemblyListFile` mehrmals in der Befehlszeile verwenden.

 Wenn Sie keine vollständigen Pfadnamen bei der Angabe der Assemblys angeben, sucht Mpgo.exe im aktuellen Verzeichnis. Wenn Sie einen falschen Pfad angeben, wird von Mpgo.exe eine Fehlermeldung ausgegeben, jedoch mit der Generierung der Daten für andere Assemblys fortgefahren. Wenn Sie eine Assembly angeben, die nicht während des Trainingsszenarios geladen wurde, werden keine Trainingsdaten für diese Assembly generiert.

 Wenn sich eine Assembly aus der Liste im globalen Assemblycache befindet, wird sie nicht aktualisiert, um die Profilinformationen zu enthalten.  Entfernen Sie sie aus dem globalen Assemblycache zum Erfassen von Profilinformationen.

 Die Verwendung von Ngen.exe und von Mpgo.exe wird nur für große verwaltete Anwendungen empfohlen, da der Vorteil vorkompilierter systemeigener Abbilder in der Regel nur deutlich wird, wenn ein erheblicher Anteil an JIT-Kompilierung zur Laufzeit eingespart wird. „mpgo.exe“ mit "Hello World"-Anwendungen auszuführen, die kein sehr umfangreiches Workingset aufweisen, bringt keine Vorteile. Möglicherweise kann „mpgo.exe“ sogar keine Profildaten erfassen.

> [!NOTE]
> Ngen.exe und Mpgo.exe werden für ASP.NET-Anwendungen und Windows Communication Foundation (WCF)-Dienste nicht empfohlen.  
  
## <a name="to-use-mpgoexe"></a>So verwenden Sie Mpgo.exe  
  
1. Verwenden Sie einen Computer, auf dem Visual Studio Ultimate 2012 und Ihre Anwendung installiert ist.  
  
2. Führen Sie Mpgo.exe als Administrator mit den erforderlichen Parametern aus.  Beispielbefehle finden Sie im nächsten Abschnitt.  
  
     Die optimierten Intermediate Language (IL)- Assemblys werden in dem Ordner erstellt, der durch den `–OutDir`-Parameter angegeben wird (in den Beispielen ist dies der Ordner `C:\Optimized` ).  
  
3. Ersetzen Sie die für Ngen.exe verwendeten IL-Assemblys mit den neuen IL-Assemblys, die die Profilinformationen von dem Verzeichnis enthalten, das mit `–OutDir` angegeben wurde.  
  
4. Das Anwendungssetup (mithilfe der von Mpgo.exe bereitgestellten Abbilder) installiert optimierte systemeigene Abbilder.  
  
## <a name="suggested-workflow"></a>Workflowvorschläge  
  
1. Erstellen Sie einen Satz optimierter IL-Assemblys, indem Sie Mpgo.exe mit dem `–Scenario`-Parameter verwenden.  
  
2. Fügen Sie der Quellcodeverwaltung die optimierten IL-Assemblys hinzu.  
  
3. Im Buildprozess rufen Sie Mpgo.exe mit dem `–Import`-Parameter als Postbuildschritt auf, um optimierte IL-Abbilder zu generieren, die „Ngen.exe“ übergeben werden.  
  
 Dieser Prozess stellt sicher, dass alle Assemblys optimierte Daten haben. Durch häufiges Einchecken aktualisierter optimierter Assemblys (Schritte 1 und 2) werden die Leistungszahlen für die gesamte Produktentwicklung konsistenter.  
  
## <a name="using-mpgoexe-from-visual-studio"></a>Verwenden von Mpgo.exe in Visual Studio  
 Sie können Mpgo.exe von Visual Studio (siehe den Artikel [Vorgehensweise: Angeben von Buildereignissen (C#)](/visualstudio/ide/how-to-specify-build-events-csharp)) mit den folgenden Einschränkungen ausführen:  
  
- Sie können Pfade in Anführungszeichen nicht mit nachgestellten Schrägstrichen verwenden, da Visual Studio-Makros standardmäßig nachgestellte Schrägstriche verwenden. (`–OutDir "C:\Output Folder\"` ist zum Beispiel ungültig.) Um diese Einschränkung zu umgehen, können Sie den nachgestellten Schrägstrich mit einem Escapezeichen versehen. (Verwenden Sie stattdessen z. B. `-OutDir "$(OutDir)\"`.)  
  
- Standardmäßig befindet sich Mpgo.exe nicht im Visual Studio-Buildpfad. Sie müssen entweder Visual Studio den Pfad hinzufügen oder auf der Mpgo-Befehlszeile den vollständigen Pfad angeben. Sie können entweder `–Scenario` oder `–Import` als Parameter im Postbuildereignis in Visual Studio angeben. Der typische Vorgang ist jedoch die einmalige Verwendung von `–Scenario` über eine Visual Studio Developer-Eingabeaufforderung. Dann wird `–Import` verwendet, um die optimierten Assemblys nach den einzelnen Builds zu aktualisieren. Beispiel: `"C:\Program Files\Microsoft Visual Studio 11.0\Team Tools\Performance Tools\mpgo.exe" -import "$(OutDir)tmp" -assemblylist "$(TargetPath)" -outdir "$(OutDir)\"`.  
  
<a name="samples"></a>   
## <a name="examples"></a>Beispiele  
 Der folgende Mpgo.exe-Befehl aus einer Developer-Eingabeaufforderung für Visual Studio optimiert eine Steuer-Anwendung:  
  
```console  
mpgo –scenario "C:\MyApp\MyTax.exe /params par" –AssemblyList Mytax.dll MyTaxUtil2011.dll –OutDir C:\Optimized –TimeOut 15  
```  
  
 Der folgende Mpgo.exe-Befehl optimiert eine Sound-Anwendung:  
  
```console  
mpgo –scenario "C:\MyApp\wav2wma.exe –input song1.wav –output song1.wma" –AssemblyList transcode.dll –OutDir C:\Optimized –TimeOut 15  
```  
  
 Der folgende Mpgo.exe-Befehl verwendet Daten aus zuvor optimierten Assemblys, um spätere Versionen der Assemblys zu optimieren:  
  
```console  
mpgo.exe -import "C:\Optimized" -assemblylist "C:\MyApp\MyTax.dll" "C:\MyApp\MyTaxUtil2011.dll" -outdir C:\ReOptimized  
```  
  
## <a name="see-also"></a>Siehe auch

- [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md)
- [Eingabeaufforderungen](developer-command-prompt-for-vs.md)
- [Improving Launch Performance for your Desktop Applications (Verbessern der Startleistung für Desktopanwendungen)](https://devblogs.microsoft.com/dotnet/improving-launch-performance-for-your-desktop-applications/)
- [Überblick Leistungsverbesserungen in .NET 4.5](https://docs.microsoft.com/archive/msdn-magazine/2012/april/clr-an-overview-of-performance-improvements-in-net-4-5)
