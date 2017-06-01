---
title: "&lt;source&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#source"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<source>-Element"
  - "source-Element"
ms.assetid: ecf86505-735d-4844-aaba-266fdd134218
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;source&gt;-Element
Gibt eine Ablaufverfolgungsquelle an, die Ablaufverfolgungsmeldungen initiiert.  
  
## Syntax  
  
```  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`name`|Optionales Attribut.<br /><br /> Gibt den Namen der Ablaufverfolgungsquelle an.|  
|`switchName`|Optionales Attribut.<br /><br /> Gibt den Namen einer Ablaufverfolgungsschalter\-Instanz in der Anwendung an.  Wenn der Schalter in einem `<switches>`\-Element nicht bezeichnet ist, wird die Schalterebene durch den Wert angegeben.|  
|`switchType`|Optionales Attribut.<br /><br /> Gibt den Typ des Ablaufverfolgungsschalters an.  Wenn das Attribut angegeben ist, muss der Typ ein gültiger Klassenname sein und darf keine leere Zeichenfolge sein.|  
|`extraAttribute`|Optionales Attribut.<br /><br /> Gibt den Wert eines für die Ablaufverfolgungsquelle spezifischen Attributs an, das von der <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A>\-Methode für diese Ablaufverfolgungsquelle ermittelt wird.|  
  
### Untergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Enthält Listener, die Meldungen sammeln, speichern und weiterleiten.|  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt die Ablaufverfolgungslistener, die Meldungen sammeln, speichern und weiterleiten, sowie die Ebene an, auf der ein Ablaufverfolgungsschalter festgelegt wird.|  
|`sources`|Enthält Ablaufverfolgungsquellen, die Ablaufverfolgungsmeldungen initiieren.|  
  
## Hinweise  
 Dieses Element kann in der Computerkonfigurationsdatei \(**Machine.config**\) und in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie die Ablaufverfolgungsquelle `mySource` mithilfe des `<source>` \-Elements hinzugefügt wird und wie die Ebene für den Quellenschalter mit der Bezeichnung `sourceSwitch` festgelegt wird.  Außerdem wird ein Ablaufverfolgungslistener für eine Konsole hinzugefügt, der Ablaufverfolgungsinformationen an die Konsole ausgibt.  
  
```  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>    
  </system.diagnostics>   
</configuration>  
```  
  
## Siehe auch  
 [Schema für Ablaufverfolgungs\- und Debugeinstellungen](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)   
 [Trace Switches](../../../../../docs/framework/debug-trace-profile/trace-switches.md)