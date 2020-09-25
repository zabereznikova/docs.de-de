---
title: <relativeBindForResources>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: daf576488e38bed28c7c0e5222bc053659372ff0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184000"
---
# <a name="relativebindforresources-element"></a>\<relativeBindForResources>-Element

Optimiert den Test für Satellitenassemblys.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a>Syntax  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob der Common Language Runtime den Test für Satellitenassemblys optimiert.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Der Test für Satellitenassemblys wird von der Laufzeit nicht optimiert. Dies ist der Standardwert.|  
|`true`|Die Laufzeit optimiert den Test für Satellitenassemblys.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Bemerkungen  

 Im allgemeinen Ressourcen-Manager Tests für Ressourcen durch, wie im Thema [Verpacken und](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) Bereitstellen von Ressourcen dokumentiert. Dies bedeutet Folgendes: Wenn Ressourcen-Manager eine bestimmte lokalisierte Version einer Ressource testet, kann Sie im globalen Assemblycache suchen, in einem kulturspezifischen Ordner in der Codebasis der Anwendung suchen, Windows Installer nach Satellitenassemblys Abfragen und das-Ereignis Auswerfen <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> . Das- `<relativeBindForResources>` Element optimiert die Art und Weise, in der Ressourcen-Manager auf Satellitenassemblys prüft Die Leistung kann bei der Überprüfung von Ressourcen unter den folgenden Bedingungen verbessert werden:  
  
- Wenn die Satellitenassembly am gleichen Speicherort wie die Codeassembly bereitgestellt wird. Anders ausgedrückt: Wenn die Codeassembly im globalen Assemblycache installiert ist, müssen auch die Satellitenassemblys dort installiert werden. Wenn die Codeassembly in der Codebasis der Anwendung installiert ist, müssen die Satellitenassemblys auch in einem kulturspezifischen Ordner in der Codebasis installiert werden.  
  
- Wenn Windows Installer nicht verwendet wird oder nur selten für die Bedarfs gesteuerte Installation von Satellitenassemblys verwendet wird.  
  
- Wenn der Anwendungscode das Ereignis nicht behandelt <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> .  
  
 `enabled`Wenn Sie das-Attribut des-Elements festlegen, wird der `<relativeBindForResources>` Ressourcen-Manager Test `true` für Satellitenassemblys wie folgt optimiert:  
  
- Der Speicherort der übergeordneten Codeassembly wird verwendet, um nach der Satellitenassembly zu suchen.  
  
- Windows Installer für Satellitenassemblys werden nicht abgefragt.  
  
- Das-Ereignis wird nicht erhoben <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> .  
  
## <a name="see-also"></a>Siehe auch

- [Verpacken und Bereitstellen von Ressourcen](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
