---
title: '&lt;RequiredRuntime&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 633769573253d7516bc50f0210c30376e6aa230a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltrequiredruntimegt-element"></a>&lt;RequiredRuntime&gt; Element
Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt. Dieses Element ist veraltet und sollte nicht mehr verwendet werden. Die [ `supportedRuntime` ](supportedruntime-element.md) -Element sollte stattdessen verwendet werden.
  
 \<configuration>  
\<Start >  
\<RequiredRuntime >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`version`|Optionales Attribut.<br /><br /> Ein Zeichenfolgenwert, der die Version von .NET Framework angibt, die diese Anwendung unterstützt. Der String-Wert muss es sich um den Namen des Verzeichnisses finden Sie unter .NET Framework-Installationsstammverzeichnis übereinstimmen. Der Inhalt des Zeichenfolgenwerts wird nicht analysiert.|  
|`safemode`|Optionales Attribut.<br /><br /> Gibt an, ob der Laufzeitstartcode, die Registrierung sucht, um die Common Language Runtime-Version zu bestimmen.|  
  
## <a name="safemode-attribute"></a>Safemode-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Der Laufzeitstartcode sucht in der Registrierung. Dies ist der Standardwert.|  
|`true`|Der Laufzeitstartcode sucht nicht in der Registrierung.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`startup`|Enthält die `<requiredRuntime>` Element.|  
  
## <a name="remarks"></a>Hinweise  
 Anwendungen, die nur Version 1.0 der Laufzeit unterstützen müssen verwenden die `<requiredRuntime>` Element. Anwendungen, die mit Version 1.1 oder höher der Runtime erstellt müssen verwenden die `<supportedRuntime>` Element.  
  
> [!NOTE]
>  Bei Verwendung der [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) Funktion, um die Konfigurationsdatei angeben, müssen Sie die `<requiredRuntime>` -Element für alle Versionen der Laufzeit. Die `<supportedRuntime>` Element wird ignoriert, wenn Sie [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
 Die `version` Attributzeichenfolge muss die Installation Ordnernamen für die angegebene Version von .NET Framework entsprechen. Diese Zeichenfolge wird nicht interpretiert werden. Wenn der Laufzeitstartcode übereinstimmenden Ordner nicht gefunden wird, wird die Common Language Runtime nicht geladen. der Startcode zeigt eine Fehlermeldung an und beendet.  
  
> [!NOTE]
>  Der Startcode für eine Anwendung, die in Microsoft Internet Explorer gehostet wird, ignoriert der `<requiredRuntime>` Element.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie die Common Language Runtime-Version in einer Konfigurationsdatei angegeben.  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Startup Settings Schema (Schema für Starteinstellungen)](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> Specifying Which Runtime Version to Use (Festlegen der zu verwendenden Runtimeversion)](http://msdn.microsoft.com/en-us/c376208d-980d-42b4-865b-fbe0d9cc97c2)
