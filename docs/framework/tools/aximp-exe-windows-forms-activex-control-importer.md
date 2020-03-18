---
title: Aximp.exe (Windows Forms ActiveX Control Importer-Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls, hosting in Windows Forms
- ActiveX Control Importer
- type definitions, converting
- Aximp.exe
- Windows Forms ActiveX Control Importer
ms.assetid: 482c0d83-7144-4497-b626-87d2351b78d0
ms.openlocfilehash: 6d58d1df81780c3033eab7c1ac3e860adeb374b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180425"
---
# <a name="aximpexe-windows-forms-activex-control-importer"></a>Aximp.exe (Windows Forms ActiveX Control Importer-Tool)
Der ActiveX Control Importer konvertiert Typdefinitionen in einer COM-Typbibliothek für ein ActiveX-Steuerelement in ein Windows Forms-Steuerelement.  
  
 Windows Forms können nur Windows Forms-Steuerelemente hosten, d. h. Klassen, die von <xref:System.Windows.Forms.Control> abgeleitet werden. "Aximp.exe" generiert eine Wrapperklasse für ein ActiveX-Steuerelement, für das ein Windows Form als Host fungieren kann. Daher stehen Ihnen dieselbe Unterstützung zur Entwurfszeit und dieselbe Programmierungsmethodik zur Verfügung, die auch für andere Windows Forms-Steuerelemente gelten.  
  
 Um das ActiveX-Steuerelement zu hosten, müssen Sie ein Wrappersteuerelement generieren, das von <xref:System.Windows.Forms.AxHost> abgeleitet wird. Dieses Wrappersteuerelement enthält eine Instanz des zugrunde liegenden ActiveX-Steuerelements. Es kann mit dem ActiveX-Steuerelement kommunizieren, wird jedoch als Windows Forms-Steuerelement angezeigt. Dieses generierte Steuerelement fungiert als Host für das ActiveX-Steuerelement und macht dessen Eigenschaften, Methoden und Ereignisse als seine eigenen verfügbar.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```console  
aximp [options]{file.dll | file.ocx}  
```  
  
## <a name="remarks"></a>Hinweise  
  
|Argument|Beschreibung|  
|--------------|-----------------|  
|*file*|Der Name der Quelldatei mit dem zu konvertierenden ActiveX-Steuerelement. Das Dateiargument muss die Erweiterung ".dll" oder ".ocx" aufweisen.|  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`/delaysign`|Legt fest, dass "Aximp.exe" das resultierende Steuerelement verzögert signiert. Diese Option müssen Sie entweder mit der Option `/keycontainer:`, `/keyfile:` oder `/publickey:` angeben. Weitere Informationen zum verzögerten Signieren finden Sie unter [Verzögertes Signieren einer Assembly](../../standard/assembly/delay-sign.md).|  
|`/help`|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|`/keycontainer:` *containerName*|Signiert die resultierende Steuerelement mit einem starken Namen, wobei das Paar aus privatem und öffentlichem Schlüssel aus dem Schlüsselcontainer verwendet wird, der mit *containername* angegeben wurde|  
|`/keyfile:` *dateiname*|Signiert das resultierende Steuerelement unter Verwendung des unter *dateiname* angegebenen Paar aus privatem und öffentlichem Schlüssel des Herausgebers mit einem starken Namen.|  
|`/nologo`|Unterdrückt die Anzeige des Startbanners von Microsoft.|  
|`/out:` *dateiname*|Legt den Namen der zu erstellenden Assembly fest.|  
|`/publickey:` *dateiname*|Signiert das resultierende Steuerelement unter Verwendung des öffentlichen Schlüssels, der in der durch *dateiname* angegebenen Datei enthalten ist, mit einem starken Namen.|  
|`/rcw:` *dateiname*|Verwendet den angegebenen Runtime Callable Wrapper, anstatt einen neuen zu generieren. Sie können mehrere Instanzen angeben. Das aktuelle Verzeichnis wird für relative Pfade verwendet. Weitere Informationen finden Sie im Abschnitt [RCW](../../standard/native-interop/runtime-callable-wrapper.md).|  
|`/silent`|Unterdrückt die Anzeige von Erfolgsmeldungen.|  
|`/source`|Erstellt C#-Quellcode für den Windows Forms-Wrapper.|  
|`/verbose`|Gibt den ausführlichen Modus an und zeigt zusätzliche Verlaufsinformationen an.|  
|`/?`|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
 "Aximp.exe" konvertiert jeweils eine vollständige Typbibliothek für ActiveX-Steuerelemente. Es erstellt eine Gruppe von Assemblys, die die Metadaten der Common Language Runtime und die Implementierung der Steuerelemente für die Typen enthalten, die in der ursprünglichen Typbibliothek definiert wurden. Die generierten Dateien werden nach dem folgenden Muster benannt:  
  
 Common Language Runtime-Proxy für COM-Typen: „*progid*.dll“  
  
 Windows Forms-Proxy für ActiveX-Steuerelemente, wobei Ax ActiveX angibt: „Ax*progid*.dll“  
  
> [!NOTE]
> Wenn der Name eines Members des ActiveX-Steuerelements mit einem in .NET Framework definierten Namen übereinstimmt, stellt "Aximp.exe" beim Erstellen der abgeleiteten AxHost-Klasse dem Membernamen das Präfix "Ctl" voran. Wenn das ActiveX-Steuerelement beispielsweise einen Member mit dem Namen "Layout" besitzt, wird dieser in der abgeleiteten AxHost-Klasse in "CtlLayout" umbenannt, da das Layout-Ereignis in .NET Framework definiert ist.  
  
 Sie können diese generierten Dateien mit Tools wie [Ildasm.exe (IL Disassembler)](ildasm-exe-il-disassembler.md) prüfen.  
  
 Die Verwendung von "Aximp.exe" zum Erstellen einer .NET-Assembly für das ActiveX-Steuerelement WebBrowser ("shdocvw.dll") wird nicht unterstützt.  
  
 Wenn Sie "Aximp.exe" für "shdocvw.dll" ausführen, wird immer eine weitere Datei mit dem Namen "shdocvw.dll" in dem Verzeichnis erstellt, in dem das Tool ausgeführt wird. Wenn diese Datei im Verzeichnis "Dokumente und Einstellungen" abgelegt wird, verursacht sie Probleme beim Ausführen von Microsoft Internet Explorer und Windows Explorer. Beim Neustart des Computers sucht Windows zuerst im Verzeichnis "Dokumente und Einstellungen" und dann erst im Verzeichnis "system32" nach einer Version von "shdocvw.dll". Zum Laden der verwalteten Wrapper verwendet Windows die im Verzeichnis "Dokumente und Einstellungen" gefundene Version. Der Grund dafür, dass Internet Explorer und Windows Explorer nicht einwandfrei funktionieren, liegt darin, dass sie auf der Rendering-Engine basieren, das in der "shdocvw.dll" im Verzeichnis "system32" enthalten ist. Falls dieses Problem auftritt, löschen Sie im Verzeichnis "Dokumente und Einstellungen" die Kopie von "shdocvw.dll", und starten Sie den Computer neu.  
  
 Wenn Sie mit "Aximp.exe" und "shdocvw.dll" eine .NET-Assembly für die Verwendung in der Anwendungsentwicklung erstellen, kann dies ebenfalls zu Problemen führen. In diesem Fall lädt die Anwendung sowohl die Systemversion als auch die erzeugte Version von "shdocvw.dll" und weist der Systemversion möglicherweise die Priorität zu. Wenn Sie in diesem Fall versuchen, im ActiveX-Steuerelement WebBrowser eine Webseite zu laden, wird möglicherweise ein Dialogfeld zum Öffnen oder Speichern angezeigt. Wenn der Benutzer auf **Öffnen** klickt, wird die Website in Internet Explorer geöffnet. Dies geschieht nur bei Computern, auf denen Internet Explorer Version 6 oder früher ausgeführt wird. Um dieses Problem zu verhindern, verwenden Sie das verwaltete <xref:System.Windows.Forms.WebBrowser>-Steuerelement oder Visual Studio, um die verwaltete Datei „shdocvw.dll“ wie in [How to: Add References to Type Libraries (Vorgehensweise: Hinzufügen von Verweisen zu Typbibliotheken)](../interop/how-to-add-references-to-type-libraries.md) beschrieben zu erstellen.  
  
## <a name="example"></a>Beispiel  
 Durch den folgenden Befehl werden "MediaPlayer.dll" und "AxMediaPlayer.dll" für das Media Player-Steuerelement `msdxm.ocx` erstellt.  
  
```console
aximp c:\systemroot\system32\msdxm.ocx  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Extras](index.md)
- [Ildasm.exe (IL-Disassembler)](ildasm-exe-il-disassembler.md)
