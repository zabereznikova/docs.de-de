---
title: <relativeBindForResources>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: 6a418fc546313b74bb965a0b223eca9c2e5acc08
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115798"
---
# <a name="relativebindforresources-element"></a>\<relativebindforresources > Element
Optimiert den Test für Satellitenassemblys.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<relativebindforresources >**  
  
## <a name="syntax"></a>Syntax  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
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
  
## <a name="remarks"></a>Hinweise  
 Im allgemeinen Ressourcen-Manager Tests für Ressourcen durch, wie im Thema [Verpacken und](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) Bereitstellen von Ressourcen dokumentiert. Dies bedeutet, dass beim Ressourcen-Manager von Tests für eine bestimmte lokalisierte Version einer Ressource möglicherweise im globalen Assemblycache gesucht wird, in einem kulturspezifischen Ordner in der Codebasis der Anwendung gesucht wird, Windows Installer nach Satellitenassemblys abgefragt wird und das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Ereignis. Das `<relativeBindForResources>`-Element optimiert die Art und Weise, in der Ressourcen-Manager Tests für Satellitenassemblys Die Leistung kann bei der Überprüfung von Ressourcen unter den folgenden Bedingungen verbessert werden:  
  
- Wenn die Satellitenassembly am gleichen Speicherort wie die Codeassembly bereitgestellt wird. Anders ausgedrückt: Wenn die Codeassembly im globalen Assemblycache installiert ist, müssen auch die Satellitenassemblys dort installiert werden. Wenn die Codeassembly in der Codebasis der Anwendung installiert ist, müssen die Satellitenassemblys auch in einem kulturspezifischen Ordner in der Codebasis installiert werden.  
  
- Wenn Windows Installer nicht verwendet wird oder nur selten für die Bedarfs gesteuerte Installation von Satellitenassemblys verwendet wird.  
  
- Wenn der Anwendungscode das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>-Ereignis nicht behandelt.  
  
 Wenn Sie das `enabled`-Attribut des `<relativeBindForResources>`-Elements auf `true` festlegen, wird Ressourcen-Manager Tests für Satellitenassemblys wie folgt optimiert:  
  
- Der Speicherort der übergeordneten Codeassembly wird verwendet, um nach der Satellitenassembly zu suchen.  
  
- Windows Installer für Satellitenassemblys werden nicht abgefragt.  
  
- Das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>-Ereignis wird nicht angehoben.  
  
## <a name="see-also"></a>Siehe auch

- [Packen und Bereitstellen von Ressourcen](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
