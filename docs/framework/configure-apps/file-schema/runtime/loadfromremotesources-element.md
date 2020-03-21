---
title: <loadFromRemoteSources>-Element
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154061"
---
# <a name="loadfromremotesources-element"></a>\<loadFromRemoteSources>-Element
Gibt an, ob Assemblys, die aus Remotequellen geladen werden, in .NET Framework 4 und höher volle Vertrauenswürdigkeit gewährt werden soll.
  
> [!NOTE]
> Wenn Sie aufgrund einer Fehlermeldung in der Visual Studio-Projektfehlerliste oder eines Buildfehlers zu diesem Artikel weitergeleitet wurden, finden Sie weitere Informationen unter [Gewusst wie: Verwenden einer Assembly aus dem Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob einer Assembly, die von einer Remotequelle geladen wird, volle Vertrauenswürdigkeit gewährt werden soll.|  
  
## <a name="enabled-attribute"></a>aktiviertes Attribut  
  
|value|Beschreibung|  
|-----------|-----------------|  
|`false`|Gewähren Sie Anwendungen aus Remotequellen keine volle Vertrauenswürdigkeit. Dies ist die Standardoption.|  
|`true`|Gewähren Sie Anwendungen aus Remotequellen volle Vertrauenswürdigkeit.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Bemerkungen

Wenn Sie in der .NET Framework 3.5- und früheren Version eine Assembly von einem Remotespeicherort laden, wird Code in der Assembly in teilweiser Vertrauenswürdigkeit mit einem Grantsatz ausgeführt, der von der Zone abhängt, aus der sie geladen wird. Wenn Sie beispielsweise eine Assembly von einer Website laden, wird sie in die Internetzone geladen und dem Internetberechtigungssatz erteilt. Mit anderen Worten, es wird in einer Internet-Sandbox ausgeführt.

Ab der .NET Framework 4-Richtlinie wird die Cas-Richtlinie (Code Access Security) deaktiviert, und Assemblys werden in voller Vertrauenswürdigkeit geladen. Normalerweise würde dies Assemblys, die mit der <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> zuvor sandkastenten Methode geladen wurden, volle Vertrauenswürdigkeit gewähren. Um dies zu verhindern, ist die Möglichkeit, Code in Assemblys auszuführen, die von einer Remotequelle geladen werden, standardmäßig deaktiviert. Wenn Sie versuchen, eine Remoteassembly zu <xref:System.IO.FileLoadException> laden, wird standardmäßig eine Ausnahmemeldung wie die folgende ausgelöst:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

Um die Assembly zu laden und ihren Code auszuführen, müssen Sie entweder Folgendes tun:

- Explizit ecreate eine Sandbox für die Assembly (siehe [Gewusst wie: Ausführen von teilweise vertrauenswürdigem Code in einer Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).

- Führen Sie den Code der Assembly in voller Vertrauenswürdigkeit aus. Dazu konfigurieren Sie `<loadFromRemoteSources>` das Element. Sie können angeben, dass die Assemblys, die in früheren Versionen von .NET Framework teilweise vertrauenswürdig ausgeführt werden, jetzt in der .NET Framework 4- und höher-Version als voll vertrauenswürdig ausgeführt werden.

> [!IMPORTANT]
> Wenn die Assembly nicht in voller Vertrauenswürdigkeit ausgeführt werden soll, legen Sie dieses Konfigurationselement nicht fest. Erstellen Sie stattdessen eine <xref:System.AppDomain> Sandbox, in die die Baugruppe geladen werden soll.

Das `enabled` Attribut `<loadFromRemoteSources>` für das Element ist nur wirksam, wenn die Codezugriffssicherheit (Code Access Security, CAS) deaktiviert ist. Standardmäßig ist die CAS-Richtlinie in der .NET Framework 4- und höher-Version deaktiviert. Wenn Sie `enabled` `true`auf festlegen, wird Remoteassemblys volle Vertrauenswürdigkeit gewährt.

Wenn `enabled` nicht auf `true`gesetzt <xref:System.IO.FileLoadException> ist, wird a unter einer der folgenden Bedingungen ausgelöst:

- Das Sandboxing-Verhalten der aktuellen Domäne unterscheidet sich von ihrem Verhalten in .NET Framework 3.5. Dazu muss die CAS-Richtlinie deaktiviert und die aktuelle Domäne nicht sandkastenweise.

- Die geladene Assembly stammt `MyComputer` nicht aus der Zone.

Festlegen `<loadFromRemoteSources>` des `true` Elements, dass diese Ausnahme nicht ausgelöst wird. Sie können angeben, dass Sie sich nicht auf die Common Language-Laufzeit verlassen, um die geladenen Assemblys zur Sicherheit zu sandboxen, und dass sie in voller Vertrauenswürdigkeit ausgeführt werden können.

## <a name="notes"></a>Notizen

- In der Version .NET Framework 4.5 und höher werden Assemblys auf lokalen Netzwerkfreigaben standardmäßig als voll vertrauenswürdig ausgeführt. Sie müssen das `<loadFromRemoteSources>` Element nicht aktivieren.

- Wenn eine Anwendung aus dem Web kopiert wurde, wird sie von Windows als Webanwendung gekennzeichnet, auch wenn sie sich auf dem lokalen Computer befindet. Sie können diese Bezeichnung ändern, indem Sie ihre `<loadFromRemoteSources>` Dateieigenschaften ändern, oder Sie können das Element verwenden, um der Assembly volle Vertrauenswürdigkeit zu gewähren. Alternativ können Sie die <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> Methode verwenden, um eine lokale Assembly zu laden, die vom Betriebssystem als aus dem Web geladen gekennzeichnet wurde.

- Möglicherweise erhalten <xref:System.IO.FileLoadException> Sie eine in einer Anwendung, die in einer Windows Virtual PC-Anwendung ausgeführt wird. Dies kann passieren, wenn Sie versuchen, eine Datei aus verknüpften Ordnern auf dem Hostingcomputer zu laden. Sie kann auch auftreten, wenn Sie versuchen, eine Datei aus einem Ordner zu laden, der über [Remotedesktopdienste](/windows/win32/termserv/terminal-services-portal) (Terminaldienste) verknüpft ist. Um die Ausnahme `enabled` zu `true`vermeiden, legen Sie auf fest.

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element wird in der Regel in der Anwendungskonfigurationsdatei verwendet, kann jedoch je nach Kontext in anderen Konfigurationsdateien verwendet werden. Weitere Informationen finden Sie im Artikel [Weitere implizite Verwendungen von CAS-Richtlinien: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) im .NET Security-Blog.  

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Assemblys, die aus Remotequellen geladen werden, volle Vertrauenswürdigkeit gewähren.

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>Weitere Informationen

- [Implizitere Verwendungen der CAS-Richtlinie: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [Gewusst wie: Ausführen von teilweise vertrauenswürdigem Code in einer Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
