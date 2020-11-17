---
title: Winmdexp.exe (Windows-Runtime-Metadaten-Exporttool)
description: Informationen zu „Winmdexp.exe“, dem Windows-Runtime-Tool für den Export von Metadaten. Dieses Tool transformiert ein .NET-Modul in eine Datei, die Windows-Runtime-Metadaten enthält.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Runtime Metadata Export Tool
- Winmdexp.exe
ms.assetid: d2ce0683-343d-403e-bb8d-209186f7a19d
ms.openlocfilehash: 42a57334f9f3e50a4d3c3ec48d57d26357d57510
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439494"
---
# <a name="winmdexpexe-windows-runtime-metadata-export-tool"></a>Winmdexp.exe (Windows-Runtime-Metadaten-Exporttool)

Das Windows-Runtime-Metadatenexport-Tool (Winmdexp.exe) transformiert ein .NET Framework-Modul in eine Datei, die Windows-Runtime-Metadaten enthält. Obwohl .NET Framework-Assemblys und Windows-Runtime-Metadatendateien dasselbe physische Format haben, gibt es Unterschiede bezüglich des Inhalts der Metadatentabellen, was bedeutet, dass .NET Framework-Assemblys nicht automatisch als Komponenten für Windows-Runtime verwendet werden können. Der Prozess des Konvertierens eines .NET Framework-Moduls in eine Komponente für Windows-Runtime wird als *Exportieren* bezeichnet. In .NET Framework 4.5 und .NET Framework 4.5.1 enthält die resultierende Windows-Metadatendatei (.winmd) sowohl die Metadaten als auch die Implementierung.  
  
 Wenn Sie die Vorlage **Komponente für Windows-Runtime**, die im **Windows Store** zu finden ist, für C# und Visual Basic in Visual Studio 2013 oder Visual Studio 2012 verwenden, ist das Compilerziel eine WINMDOBJ-Datei. Ein nachfolgender Buildschritt ruft „Winmdexp.exe“ auf, um die WINMDOBJ-Datei in eine WINMD-Datei zu exportieren. Dies ist die empfohlene Methode zum Erstellen einer Komponente für Windows-Runtime. Verwenden Sie "Winmdexp.exe" direkt, wenn Sie mehr Kontrolle über den Buildvorgang möchten, als Visual Studio bietet.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```console  
winmdexp [options] winmdmodule  
```  
  
## <a name="parameters"></a>Parameter  
  
|Argument oder Option|Beschreibung|  
|------------------------|-----------------|  
|`winmdmodule`|Gibt das zu exportierende Modul (.winmdobj) an. Nur ein Modul ist erlaubt. Um dieses Modul zu erstellen, verwenden Sie die `/target`-Compileroption mit dem `winmdobj`-Ziel. Weitere Informationen finden Sie unter [-target:winmdobj (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md) oder [-target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`/docfile:` `docfile`<br /><br /> `/d:` `docfile`|Gibt die XML-Dokumentations-Ausgabedatei an, die "Winmdexp.exe" erzeugt. In .NET Framework 4.5 entspricht die Ausgabedatei im Wesentlichen der XML-Dokumentationseingabedatei.|  
|`/moduledoc:` `docfile`<br /><br /> `/md:` `docfile`|Gibt den Namen der XML-Dokumentationsdatei an, die der Compiler mit `winmdmodule` produzierte.|  
|`/modulepdb:` `symbolfile`<br /><br /> `/mp:` `symbolfile`|Gibt den Namen der Programmdatenbankdatei (PDB-Datei) an, die Symbole für `winmdmodule` enthält.|  
|`/nowarn:` `warning`|Unterdrückt die angegebene Warnungsanzahl. Für *warning* stellen Sie nur den numerischen Teil des Fehlercodes bereit, ohne führende Nullen.|  
|`/out:` `file`<br /><br /> `/o:` `file`|Gibt den Namen der Windows-Metadatendatei (.winmd) für die Ausgabe an.|  
|`/pdb:` `symbolfile`<br /><br /> `/p:` `symbolfile`|Gibt den Namen der Programmdatenbank-Ausgabedatei (PDB-Datei) an, die die Symbole für die exportierte Windows-Metadatendatei (.winmd) enthält.|  
|`/reference:` `winmd`<br /><br /> `/r:` `winmd`|Gibt eine Metadatendatei (WINMD-Datei oder Assembly) an, auf die während des Exports verwiesen wird. Wenn Sie die Verweisassemblys unter „\Programme (x86)\Reference Assemblies\Microsoft\Framework\\.NETCore\v4.5“ („\Programme\\...“ auf 32-Bit-Computern) verwenden, fügen Sie Verweise sowohl auf „System.Runtime.dll“ als auch auf „mscorlib.dll“ mit ein.|  
|`/utf8output`|Gibt an, dass die Ausgabemeldungen UTF-8-Codierung aufweisen sollten.|  
|`/warnaserror+`|Gibt an, dass alle Warnungen als Fehler behandelt werden sollen.|  
|**@** `responsefile`|Gibt eine Antwortdatei (.rsp) an, die Optionen enthält (und optional `winmdmodule`). Jede Zeile in `responsefile` sollte ein einzelnes Argument oder eine einzelne Option enthalten.|  
  
## <a name="remarks"></a>Hinweise  

 "Winmdexp.exe" kann nicht verwendet werden, um eine beliebige .NET Framework-Assembly in eine WINMD-Datei zu konvertieren. Ein Modul ist erforderlich, das mit der `/target:winmdobj`-Option kompiliert wird, und es gelten zusätzliche Einschränkungen. Die wichtigste dieser Einschränkungen besteht darin, dass alle Typen, die in der API-Schnittstelle der Assembly verfügbar gemacht werden, Windows-Runtime-Typen sein müssen. Weitere Informationen finden Sie im Abschnitt „Deklarieren von Typen in Windows-Runtime-Komponenten“ des Artikels [Erstellen von Windows-Runtime-Komponenten in C# und Visual Basic](/previous-versions/br230301(v=vs.110)).
  
 Wenn Sie eine Windows 8.x Store-App oder eine Komponente für Windows-Runtime mit C# oder Visual Basic schreiben, bietet .NET Framework Unterstützung für das einfachere Programmieren mit der Windows-Runtime. Dies wird im Artikel [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../cross-platform/support-for-windows-store-apps-and-windows-runtime.md) behandelt. Während dieses Vorgangs werden einige häufig verwendete Windows-Runtime-Typen .NET Framework-Typen zugeordnet. „Winmdexp.ex“e kehrt diesen Prozess um und erzeugt eine API-Schnittstelle, die die entsprechenden Windows-Runtime-Typen verwendet. So werden beispielsweise Typen, die aus der <xref:System.Collections.Generic.IList%601>-Schnittstelle erstellt werden, Typen zugeordnet, die über die <xref:Windows.Foundation.Collections.IVector%601>-Schnittstelle von Windows-Runtime erstellt werden.  
  
## <a name="see-also"></a>Siehe auch

- [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
- [Erstellen von Windows-Runtime-Komponenten in C# und Visual Basic](/previous-versions/br230301(v=vs.110))
- [Winmdexp.exe-Fehlermeldungen](winmdexp-exe-error-messages.md)
- [Build-, Bereitstellungs- und Konfigurationstools (.NET Framework)](/previous-versions/dotnet/netframework-4.0/dd233108(v=vs.100))
