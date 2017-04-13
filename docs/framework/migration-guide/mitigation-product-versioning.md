---
title: "Migration: Produktversionsverwaltung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Migration: Produktversionsverwaltung
In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und 4.6.1 wurde die Produktversionsverwaltung im Vergleich zu früheren Versionen von .NET Framework \(.NET Framework 4, 4.5, 4.5.1 und 4.5.2\) geändert.  
  
## Änderungen hinsichtlich der Produktversionsverwaltung  
 Im Folgenden finden Sie die detaillierten Änderungen:  
  
-   Der Wert des `Version`\-Eintrags im `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`\-Schlüssel wurde in `4.6.`*xxxxx* geändert. In .NET Framework 4.5, 4.5.1 und 4.5.2 lautete das Format `4.5.`*xxxxx*.  
  
-   Die Datei\- und die Produktversionsverwaltung für .NET Framework\-Dateien wurde vom früheren Versionsschema `4.0.30319.x` in `4.6.X.0` geändert. Sie können diese neuen Werte anzeigen, wenn Sie die **Eigenschaften** der Datei anzeigen, indem Sie mit der rechten Maustaste auf eine Datei klicken.  
  
-   Die Attribute <xref:System.Reflection.AssemblyFileVersionAttribute> und <xref:System.Reflection.AssemblyInformationalVersionAttribute> für verwaltete Assemblys verfügen über <xref:System.Version>\-Werte im Formular `4.6.X.0`  
  
-   In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] und 4.6.1 gibt die <xref:System.Environment.Version%2A?displayProperty=fullName>\-Eigenschaft die korrigierte Versionszeichenfolge `4.0.30319.42000` zurück. In .NET Framework 4, 4.5, 4.5.1 und 4.5.2 gab die Eigenschaft Versionszeichenfolgen im Format `4.0.30319.xxxxx` zurück \(z. B. "4.0.30319.18010"\). Es wird nicht empfohlen, eine neue Abhängigkeit von der <xref:System.Environment.Version%2A?displayProperty=fullName>\-Eigenschaft in Anwendungscode zu verwenden.  
  
### Behandeln der Änderungen hinsichtlich der Produktversionsverwaltung  
 Im Allgemeinen sollten Anwendungen von den empfohlenen Verfahren zum Erkennen solcher Faktoren, wie beispielsweise die Laufzeitversion von .NET Framework und das Installationsverzeichnis, abhängen:  
  
-   Wie Sie die Laufzeitversion von .NET Framework ermitteln, erfahren Sie unter [Gewusst wie: Bestimmen der installierten .NET Framework\-Versionen](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).  
  
-   Um den Installationspfad für .NET Framework zu ermitteln, verwenden Sie den Wert des `InstallPath`\-Eintrags im `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` Schlüssel.  
  
    > [!IMPORTANT]
    >  Der Name des Unterschlüssels ist `NET Framework Setup` und nicht `.NET Framework Setup`.  
  
-   Um den Verzeichnispfad für die .NET Framework Common Language Runtime zu bestimmen, rufen Sie die <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=fullName>\-Methode auf.  
  
-   Um die CLR\-Version zu erhalten, rufen Sie die <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=fullName>\-Methode auf.   Für .NET Framework 4 und die dazugehörigen Punktversionen \(.NET Framework 4.5, 4.5.1, 4.5.2 und [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] sowie 4.6.1\) wird die Zeichenfolge `v4.0.30319` zurückgegeben.  
  
## Siehe auch  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)