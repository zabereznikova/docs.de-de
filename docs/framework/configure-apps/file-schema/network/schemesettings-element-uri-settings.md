---
title: "&lt;schemeSettings&gt;-Element (Uri-Einstellungen) | Microsoft Docs"
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
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# &lt;schemeSettings&gt;-Element (Uri-Einstellungen)
Gibt an, wie ein <xref:System.Uri>\-Objekt für bestimmte Schemen analysiert wird.  
  
## Syntax  
  
```  
  
      <schemeSettings>   
</schemeSettings>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Kein  
  
### Untergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-schemesettings-uri-settings.md)|Fügt eine Schemaeinstellung für einen Schemanamen hinzu.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-schemesettings-uri-settings.md)|Löscht alle vorhandenen Schemaeinstellungen.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-schemesettings-uri-settings.md)|Entfernt eine Schemaeinstellung für einen Schemanamen.|  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[uri](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|Enthält Einstellungen, die angeben, wie .NET Framework durch URIs \(Uniform Resource Identifier\) ausgedrückte Webadressen behandelt.|  
  
## Hinweise  
 Standardmäßig entfernt die <xref:System.Uri?displayProperty=fullName>\-Klasse Escapezeichen aus als Prozentwert codierte Pfadtrennzeichen vor dem Ausführen der Pfadkomprimierung.  Dies wurde als Sicherheitsmechanismus gegen Angriffe implementiert. Beispiel:  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Wenn dieser URI an Module übergeben wird und als Prozentwert codierte Zeichen nicht ordnungsgemäß behandelt werden, kann dies dazu führen, dass vom Server der folgende Befehl ausgeführt wird:  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 Aus diesem Grund entfernt die <xref:System.Uri?displayProperty=fullName>\-Klasse zuerst Escapezeichen aus Pfadtrennzeichen und wendet dann die Pfadkomprimierung an.  Das Übergeben der böswilligen URL oben an den <xref:System.Uri?displayProperty=fullName>\-Klassenkonstruktor führt zum folgenden URI:  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 Dieses Standardverhalten kann so abgeändert werden, dass aus prozentcodierten Pfadtrennzeichen, die die schemeSettings\-Konfigurationsoption für ein bestimmtes Schema verwenden, die Escapezeichen nicht gelöscht werden.  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird ebenfalls eine von der <xref:System.Uri>\-Klasse verwendete Konfiguration gezeigt, die das Nichthinzufügen von Escapezeichen zu als Prozentwert codierten Pfadabgrenzungszeichen für das HTTP\-Schema unterstützt.  
  
```  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## Elementinformationen  
  
|||  
|-|-|  
|Namespace|System|  
|Schemaname||  
|Validierungsdatei||  
|Kann leer sein||  
  
## Siehe auch  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=fullName>   
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=fullName>   
 <xref:System.Configuration.UriSection?displayProperty=fullName>   
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=fullName>   
 <xref:System.GenericUriParserOptions?displayProperty=fullName>   
 <xref:System.Uri?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)