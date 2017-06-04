---
title: "&lt;requiredRuntime&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<requiredRuntime>-Element"
  - "Containertags, <requiredRuntime>-Element"
  - "requiredRuntime-Element"
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;requiredRuntime&gt;-Element
Gibt an, dass die Anwendung lediglich Version 1.0 der Common Language Runtime unterstützt.  
  
## Syntax  
  
```  
  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`version`|Optionales Attribut.<br /><br /> Ein Zeichenfolgenwert, der angibt, welche Version von .NET Framework von dieser Anwendung unterstützt wird.  Der Zeichenfolgenwert muss dem Verzeichnis im Stammverzeichnis für die Installation von .NET Framework entsprechen.  Der Inhalt des Zeichenfolgenwerts wird nicht analysiert.|  
|`safemode`|Optionales Attribut.<br /><br /> Gibt an, ob der Runtimestartcode die Registrierung durchsucht, um die Runtimeversion zu ermitteln.|  
  
## safemode\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Der Laufzeitstartcode sieht in der Registrierung nach.  Dies ist der Standardwert.|  
|`true`|Der Laufzeitstartcode sieht nicht in der Registrierung nach.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`startup`|Enthält das `<requiredRuntime>`\-Element.|  
  
## Hinweise  
 Anwendungen, die nur Version 1.0 der Laufzeit unterstützen, müssen das `<requiredRuntime>`\-Element verwenden.  Anwendungen, die mit Version 1.1 oder einer höheren Version der Laufzeit erstellt wurden, müssen das `<supportedRuntime>`\-Element verwenden.  
  
> [!NOTE]
>  Wenn Sie die Konfigurationsdatei mithilfe der [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)\-Funktion angeben, müssen Sie das `<requiredRuntime>`\-Element für alle Versionen der Laufzeit verwenden.  Das `<supportedRuntime>`\-Element wird ignoriert, wenn Sie [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) verwenden.  
  
 Die `version`\-Attributzeichenfolge muss mit dem Namen des Installationsordners für die angegebene Version von .NET Framework übereinstimmen.  Diese Zeichenfolge wird nicht interpretiert.  Findet der Runtimestartcode keinen übereinstimmenden Ordner, wird die Runtime nicht geladen. Der Startcode gibt eine Fehlermeldung aus und beendet dann das Programm.  
  
> [!NOTE]
>  Der Startcode für eine Anwendung, die in Microsoft Internet Explorer gehostet wird, ignoriert das `<requiredRuntime>`\-Element.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie die Runtimeversion in einer Konfigurationsdatei angeben.  
  
```  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Starteinstellungen](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/de-de/c376208d-980d-42b4-865b-fbe0d9cc97c2)