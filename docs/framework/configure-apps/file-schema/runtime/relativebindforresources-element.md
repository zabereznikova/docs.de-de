---
title: <relativeBindForResources>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153905"
---
# <a name="relativebindforresources-element"></a>\<relativeBindForResources> Element
Optimiert den Test für Satellitenassemblys.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a>Syntax  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Common Language Runtime den Prüfpunkt für Satellitenassemblys optimiert.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Laufzeit optimiert den Prüfpunkt für Satellitenassemblys nicht. Dies ist der Standardwert.|  
|`true`|Die Laufzeit optimiert die Sonde für Satellitenassemblys.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Im Allgemeinen untersucht Resource Manager Ressourcen, wie im Thema [Verpackung und Bereitstellung von Ressourcen](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) dokumentiert. Dies bedeutet, dass Resource Manager, wenn er nach einer bestimmten lokalisierten Version einer Ressource sucht, im globalen Assemblycache suchen, in einem kulturspezifischen <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Ordner in der Codebasis der Anwendung suchen, Windows Installer nach Satellitenassemblys abfragen und das Ereignis aushebe. Das `<relativeBindForResources>` Element optimiert die Art und Weise, in der Resource Manager für Satellitenassemblys untersucht wird. Es kann die Leistung verbessern, wenn Ressourcen unter den folgenden Bedingungen gesucht werden:  
  
- Wenn die Satellitenassembly am gleichen Speicherort wie die Codeassembly bereitgestellt wird. Mit anderen Worten, wenn die Codeassembly im globalen Assemblycache installiert ist, müssen die Satellitenassemblys auch dort installiert werden. Wenn die Codeassembly in der Codebasis der Anwendung installiert ist, müssen die Satellitenassemblys auch in einem kulturspezifischen Ordner in der Codebasis installiert werden.  
  
- Wenn Windows Installer nicht oder nur selten für die Bedarfsinstallation von Satellitenassemblys verwendet wird.  
  
- Wenn Anwendungscode das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Ereignis nicht behandelt.  
  
 Wenn `enabled` Sie das `<relativeBindForResources>` Attribut `true` des Elements so festlegen, dass der Resource Manager-Test für Satellitenassemblys wie folgt optimiert wird:  
  
- Es verwendet die Position der übergeordneten Codeassembly, um für die Satellitenassembly zu suchen.  
  
- Windows Installer wird nicht nach Satellitenassemblys abgefragt.  
  
- Es löst nicht <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> das Ereignis aus.  
  
## <a name="see-also"></a>Weitere Informationen

- [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
