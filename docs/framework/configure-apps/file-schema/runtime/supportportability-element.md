---
title: "&lt;supportPortability&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<supportPortability>-Element"
  - "supportPortability-Element"
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# &lt;supportPortability&gt;-Element
Gibt an, dass eine Anwendung in zwei verschiedenen Implementierungen von .NET Framework durch das Deaktivieren des Standardverhaltens, das die Assemblys zu Anwendungsportabilitätszwecken als gleich behandelt, auf die gleiche Assembly verweisen kann.  
  
## Syntax  
  
```  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|PKT|Erforderliches Attribut.<br /><br /> Gibt das öffentliche Schlüsseltoken der betreffenden Assembly als Zeichenfolge an.|  
|enabled|Optionales Attribut.<br /><br /> Gibt an, ob Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework\-Assembly aktiviert werden soll.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|true|Aktivieren Sie die Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework\-Assembly.  Dies ist der Standardwert.|  
|false|Deaktivieren Sie die Unterstützung für Portabilität zwischen Implementierungen der angegebenen .NET Framework\-Assembly.  Dadurch kann die Anwendung Verweise auf mehrere Implementierungen besitzen.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
  
## Hinweise  
 Ab [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] werden Anwendungen, die beide Implementierungen von .NET Framework verwenden können, z. B. die .NET Framework\-Implementierung oder die .NET Framework für Silverlight\-Implementierung, automatisch unterstützt.  Die zwei Implementierungen einer bestimmten .NET Framework\-Assembly werden vom Assemblybinder als äquivalent betrachtet.  In einigen Szenarien verursacht diese Anwendungsportabilitätsfunktion Probleme.  In jenen Szenarien kann das `<supportPortability>`\-Element verwendet werden, um die Funktion zu deaktivieren.  
  
 Ein solches Szenario ist eine Assembly, die sowohl die .NET Framework\-Implementierung als auch die .NET Framework for Silverlight\-Implementierung einer bestimmten Verweisassembly mit Verweisen versehen muss.  Ein in Windows Presentation Foundation \(WPF\) geschriebener XAML\-Designer müsste möglicherweise sowohl auf die WPF\-Desktopimplementierung, für die Benutzeroberfläche des Designers, als auch die Teilmenge von WPF, die in der Silverlight\-Implementierung enthalten ist, verweisen.  Standardmäßig verursachen die separaten Verweise einen Compilerfehler, da die Assemblybindung die zwei Assemblys als Entsprechung ansieht.  Dieses Element deaktiviert das Standardverhalten und ermöglicht eine erfolgreiche Kompilierung.  
  
> [!IMPORTANT]
>  Damit der Compiler die Informationen an die Assemblybindungs\-Logik der Common Language Runtime übergibt, müssen Sie den Speicherort der Datei "app.config", die dieses Element enthält, mithilfe der `/appconfig`\-Compileroption angeben.  
  
## Beispiel  
 Das folgende Beispiel ermöglicht einer Anwendung, über Verweise sowohl auf die .NET Framework\-Implementierung als auch die .NET Framework for Silverlight\-Implementierung jeder die oft ausgegebene Befehlszeilen  .NET Framework\-Assembly, die in beiden Implementierungen vorhanden ist, zu verfügen.  Mit der `/appconfig`\-Compileroption muss der Speicherort dieser app.config\-Datei angegeben werden.  
  
```  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [\/appconfig \(C\#\-Compileroptionen\)](http://msdn.microsoft.com/library/ee523958.aspx)   
 [.NET Framework Assembly Unification Overview](http://msdn.microsoft.com/de-de/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)