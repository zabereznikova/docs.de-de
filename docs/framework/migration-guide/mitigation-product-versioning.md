---
title: 'Entschärfung: Produktversionsverwaltung'
ms.date: 03/30/2017
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 483a6532ad62fb7e1561ac5cc4de37aeaaf45fa7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33389404"
---
# <a name="mitigation-product-versioning"></a>Entschärfung: Produktversionsverwaltung
In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und höher wurde die Produktversionsverwaltung im Vergleich zu früheren Releases von .NET Framework (.NET Framework 4, 4.5, 4.5.1 und 4.5.2) geändert.  
  
## <a name="product-versioning-changes"></a>Änderungen hinsichtlich der Produktversionsverwaltung  
 Im Folgenden finden Sie die detaillierten Änderungen:  
  
-   Der Wert des `Version`-Eintrags im `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`-Schlüssel wurde für .NET Framework 4.6 und dessen Punktreleases in `4.6.`*xxxxx* und für .NET Framework 4.7 in `4.7.`*xxxxx* geändert. In .NET Framework 4.5, 4.5.1 und 4.5.2 lautete das Format `4.5.`*xxxxx*.  
  
-   Die Datei- und Produktversionsverwaltung für .NET Framework-Dateien wurde vom früheren Schema der Versionsverwaltung von `4.0.30319.x` in `4.6.X.0` (für .NET Framework 4.6 und dessen Punktreleases) sowie in `4.7.X.0` (für .NET Framework 4.7 und dessen Punktreleases) geändert. Sie können diese neuen Werte anzeigen, wenn Sie die **Eigenschaften** der Datei anzeigen, indem Sie mit der rechten Maustaste auf eine Datei klicken.  
  
-   Die Attribute <xref:System.Reflection.AssemblyFileVersionAttribute> und <xref:System.Reflection.AssemblyInformationalVersionAttribute> für verwaltete Assemblys verfügen über <xref:System.Version>-Werte im Format `4.6.X.0` für .NET Framework 4.6 und die zugehörigen Punktversionen sowie `4.7.X.0` für .NET Framework 4.7.  
  
-   In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], 4.6.1, 4.6.2 und 4.7, gibt die <xref:System.Environment.Version%2A?displayProperty=nameWithType>-Eigenschaft die korrigierte Versionszeichenfolge `4.0.30319.42000` zurück. In .NET Framework 4, 4.5, 4.5.1 und 4.5.2 hat die Eigenschaft Versionszeichenfolgen im Format `4.0.30319.xxxxx` zurückgegeben (z. B. „4.0.30319.18010“). Es wird nicht empfohlen, eine neue Abhängigkeit von der <xref:System.Environment.Version%2A?displayProperty=nameWithType>-Eigenschaft in Anwendungscode zu verwenden.  
  
### <a name="handling-the-product-versioning-changes"></a>Behandeln der Änderungen hinsichtlich der Produktversionsverwaltung  
 Im Allgemeinen sollten Anwendungen von den empfohlenen Verfahren zum Erkennen solcher Faktoren, wie beispielsweise die Laufzeitversion von .NET Framework und das Installationsverzeichnis, abhängen:  
  
-   Weitere Informationen zum Erkennen der Laufzeitversion von .NET Framework finden Sie unter [Gewusst wie: Bestimmen der installierten .NET Framework-Versionen](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).  
  
-   Um den Installationspfad für .NET Framework zu ermitteln, verwenden Sie den Wert des `InstallPath`-Eintrags im `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` Schlüssel.  
  
    > [!IMPORTANT]
    >  Der Name des Unterschlüssels ist `NET Framework Setup` und nicht `.NET Framework Setup`.  
  
-   Um den Verzeichnispfad für die .NET Framework Common Language Runtime zu bestimmen, rufen Sie die <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType>-Methode auf.  
  
-   Um die CLR-Version zu erhalten, rufen Sie die <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType>-Methode auf.   Für .NET Framework 4 und die dazugehörigen Punktreleases (.NET Framework 4.5, 4.5.1, 4.5.2 und [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] sowie 4.6.1, 4.6.2 und 4.7) wird die Zeichenfolge `v4.0.30319` zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
 
