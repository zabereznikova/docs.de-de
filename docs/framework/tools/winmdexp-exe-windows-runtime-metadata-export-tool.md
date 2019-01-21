---
title: Winmdexp.exe (Windows-Runtime-Metadaten-Exporttool)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Runtime Metadata Export Tool
- Winmdexp.exe
ms.assetid: d2ce0683-343d-403e-bb8d-209186f7a19d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 434d5dd002124033f6d7cf5104d87264ee9c0388
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222219"
---
# <a name="winmdexpexe-windows-runtime-metadata-export-tool"></a>Winmdexp.exe (Windows-Runtime-Metadaten-Exporttool)
Das [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Metadatenexport-Tool (Winmdexp.exe) transformiert ein .NET Framework-Modul in eine Datei, die [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Metadaten enthält. Obwohl .NET Framework-Assemblys und [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Metadatendateien dasselbe physische Format verwenden, gibt es Unterschiede bezüglich des Inhalts der Metadatentabellen, d. h. dass .NET Framework-Assemblys nicht automatisch als [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponenten verwendet werden können. Der Prozess des Konvertierens eines .NET Framework-Moduls in eine [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Komponente wird als *Exportieren* bezeichnet. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] und [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] enthält die resultierende Windows-Metadatendatei (.winmd) sowohl Metadaten als auch Implementierung.  
  
 Wenn Sie die Vorlage **[!INCLUDE[wrt](../../../includes/wrt-md.md)] Component**, die im **Windows Store** zu finden ist, für C# und Visual Basic in Visual Studio 2013 oder Visual Studio 2012 verwenden, ist das Compilerziel eine WINMDOBJ-Datei, und ein nachfolgender Buildschritt ruft „Winmdexp.exe“ auf, um die WINMDOBJ-Datei in eine WINMD-Datei zu exportieren. Dies ist die empfohlene Methode, eine Komponente für [!INCLUDE[wrt](../../../includes/wrt-md.md)] zu erstellen. Verwenden Sie "Winmdexp.exe" direkt, wenn Sie mehr Kontrolle über den Buildvorgang möchten, als Visual Studio bietet.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```  
winmdexp [options] winmdmodule  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Argument oder Option|Beschreibung|  
|------------------------|-----------------|  
|`winmdmodule`|Gibt das zu exportierende Modul (.winmdobj) an. Nur ein Modul ist erlaubt. Um dieses Modul zu erstellen, verwenden Sie die `/target`-Compileroption mit dem `winmdobj`-Ziel. Weitere Informationen finden Sie unter [/target:winmdobj (C#-Compileroptionen)](~/docs/csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md) oder [/target (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/target.md).|  
|`/docfile:` `docfile`<br /><br /> `/d:` `docfile`|Gibt die XML-Dokumentations-Ausgabedatei an, die "Winmdexp.exe" erzeugt. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] entspricht die Ausgabedatei im Wesentlichen der XML-Dokumentations-Eingabedatei.|  
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
 "Winmdexp.exe" kann nicht verwendet werden, um eine beliebige .NET Framework-Assembly in eine WINMD-Datei zu konvertieren. Ein Modul ist erforderlich, das mit der `/target:winmdobj`-Option kompiliert wird, und es gelten zusätzliche Einschränkungen. Die wichtigste dieser Einschränkungen besteht darin, dass alle Typen, die in der API-Schnittstelle der Assembly verfügbar gemacht werden, [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Typen sein müssen. Weitere Informationen finden Sie im Abschnitt „Deklarieren von Typen in Windows-Runtime-Komponenten“ des Artikels [Erstellen von Windows-Runtime-Komponenten in C# und Visual Basic](https://go.microsoft.com/fwlink/p/?LinkID=238313) im Windows Developer Center.  
  
 Wenn Sie eine [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]-App oder eine Komponente für [!INCLUDE[wrt](../../../includes/wrt-md.md)] mit C# oder Visual Basic schreiben, bietet .NET Framework Unterstützung für das einfachere Programmieren mit der [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Dies wird im Artikel [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) behandelt. Während dieses Vorgangs werden einige häufig verwendete [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Typen .NET Framework-Typen zugeordnet. "Winmdexp.exe" kehrt diesen Prozess um und erzeugt eine API-Schnittstelle, die die entsprechenden [!INCLUDE[wrt](../../../includes/wrt-md.md)]-Typen verwendet. So werden beispielsweise Typen, die aus der <xref:System.Collections.Generic.IList%601>-Schnittstelle erstellt werden, Typen zugeordnet, die aus der [!INCLUDE[wrt](../../../includes/wrt-md.md)][IVector\<T>](https://go.microsoft.com/fwlink/p/?LinkId=251132)-Schnittstelle erstellt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)  
 [Erstellen von Windows-Runtime-Komponenten in C# und Visual Basic](https://go.microsoft.com/fwlink/p/?LinkID=238313)  
 [Winmdexp.exe-Fehlermeldungen](../../../docs/framework/tools/winmdexp-exe-error-messages.md)  
 [Build-, Bereitstellungs- und Konfigurationstools (.NET Framework)](https://msdn.microsoft.com/library/b8c921be-6012-4181-b8d4-ab15813fc9a7)
