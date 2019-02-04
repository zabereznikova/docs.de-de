---
title: <loadFromRemoteSources>-Element
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7568129f30267b212737ec8aa688cf882e19bbff
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675308"
---
# <a name="loadfromremotesources-element"></a>\<LoadFromRemoteSources >-Element
Gibt an, ob Assemblys aus Remotequellen geladen volle Vertrauenswürdigkeit in .NET Framework 4 und höher gewährt werden soll.
  
> [!NOTE]
>  Wenn Sie aufgrund einer Fehlermeldung in der Fehlerliste von Visual Studio-Projekt oder einen Buildfehler zu diesem Artikel weitergeleitet wurden, finden Sie unter [Vorgehensweise: Verwenden Sie eine Assembly aus dem Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).  
  
 \<configuration>  
\<runtime>  
\<loadFromRemoteSources>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob eine Assembly, die von einer Remotequelle geladen wird, volle Vertrauenswürdigkeit gewährt werden soll.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Gewähren Sie volle Vertrauenswürdigkeit nicht auf Anwendungen aus Remotequellen. Dies ist die Standardeinstellung.|  
|`true`|Gewähren Sie volle Vertrauenswürdigkeit auf Anwendungen aus Remotequellen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise

Wenn Sie eine Assembly von einem Remotestandort befindet, Laden in das .NET Framework 3.5 und früheren Versionen wird Code in der Assembly bei teilweiser Vertrauenswürdigkeit mit einem Berechtigungssatz, der die Zone hängt von dem es geladen wird ausgeführt. Z. B. Wenn Sie eine Assembly von einer Website laden, handelt es sich dabei in der Internetzone geladen den Internet-Berechtigungssatz. Das heißt, führt er in einem Internet-Sandkasten.

Ab .NET Framework 4, Richtlinie für die Codezugriffssicherheit (CAS) ist deaktiviert, und Assemblys mit voller Vertrauenswürdigkeit geladen werden. Normalerweise würde diese Assemblys geladen und volle Vertrauenswürdigkeit gewähren der <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> Methode, die zuvor Sandbox waren. Um dies zu verhindern, ist die Möglichkeit zum Ausführen von Code in Assemblys, die von einer Remotequelle geladen, standardmäßig deaktiviert. Standardmäßig, wenn Sie versuchen, eine Remoteassembly, laden ein <xref:System.IO.FileLoadException> mit eine Ausnahmemeldung wie, dass Sie Folgendes ausgelöst wird:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported. 
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' ---> 
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly 
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default, 
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch. 
```

Zum Laden der Assembly und deren Code ausführen, müssen Sie entweder:

- Erstellen Sie explizit einen Sandkasten für die Assembly (finden Sie unter [Vorgehensweise: Ausführen von teilweise vertrauenswürdigem Code in einer Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).

- Führen Sie Code von der Assembly mit voller Vertrauenswürdigkeit. Konfigurieren Sie dazu die `<loadFromRemoteSources>` Element. Sie können angeben, dass die Assemblys, die bei teilweiser Vertrauenswürdigkeit in früheren Versionen von .NET Framework ausgeführt werden jetzt als voll vertrauenswürdig in der .NET Framework 4 und höher ausführen.

> [!IMPORTANT]
> Wenn die Assembly nicht mit voller Vertrauenswürdigkeit ausgeführt werden soll, legen Sie dieses Element nicht. Erstellen Sie stattdessen eine Sandbox <xref:System.AppDomain> in dem die Assembly zu laden.

Die `enabled` -Attribut für die `<loadFromRemoteSources>` Element gilt nur, wenn die Codezugriffssicherheit (CAS) deaktiviert ist. Standardmäßig ist die CAS-Richtlinie in der .NET Framework 4 und höheren Versionen deaktiviert. Setzen Sie `enabled` zu `true`, remote-Assemblys die volle Vertrauenswürdigkeit gewährt werden.

Wenn `enabled` ist nicht festgelegt, um `true`, <xref:System.IO.FileLoadException> wird in einer der folgenden Bedingungen ausgelöst:

- Der Sandkasten-Verhalten der aktuellen Domäne unterscheidet sich vom Verhalten in .NET Framework 3.5. Dies erfordert die CAS-Richtlinie deaktiviert werden soll, und der aktuellen Domäne nicht zu Sandbox.

- Die geladene Assembly stammt nicht von der `MyComputer` Zone.

Festlegen der `<loadFromRemoteSources>` Element `true` wird verhindert, dass diese Ausnahme ausgelöst wird. Damit können Sie angeben, dass nicht Sie sich die common Language Runtime für das Sandboxing die geladenen Assemblys für die Sicherheit verlassen und ermöglicht werden kann. Führen Sie in volle Vertrauenswürdigkeit.

## <a name="notes"></a>Hinweise

- In der .NET Framework 4.5 und höheren Versionen wird standardmäßig Assemblys auf der lokalen Netzwerkfreigaben mit voller Vertrauenswürdigkeit ausgeführt; Sie müssen keine aktivieren die `<loadFromRemoteSources>` Element.

- Wenn eine Anwendung über das Web kopiert wurde, wird er von Windows als replikationsbereit markiert eine Webanwendung, auch wenn er auf dem lokalen Computer befindet. Sie können diese Bezeichnung durch Ändern der Dateieigenschaften ändern, oder Sie können die `<loadFromRemoteSources>` Element gewähren Sie die Assembly volle Vertrauenswürdigkeit. Als Alternative können Sie die <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> Methode, um eine lokale Assembly zu laden, die das Betriebssystem gekennzeichnet wurden, als aus dem Web geladen wurde.

- Sie erhalten möglicherweise eine <xref:System.IO.FileLoadException> in einer Anwendung, die in einer Windows Virtual PC-Anwendung ausgeführt wird. Dies kann passieren, wenn Sie versuchen, eine Datei aus dem verknüpften Ordner auf dem Hostcomputer zu laden. Er kann auch auftreten, wenn Sie versuchen, eine Datei aus einem Ordner, die über verknüpfte laden [Remote Desktop Services](https://go.microsoft.com/fwlink/?LinkId=182775) (Terminaldienste). Um die Ausnahme zu vermeiden, legen Sie `enabled` zu `true`.

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element wird in der Regel in der Konfigurationsdatei der Anwendung verwendet, aber in anderen Konfigurationsdateien, die je nach Kontext verwendet werden kann. Weitere Informationen finden Sie im Artikel [Weitere implizite verwendet der CAS-Richtlinie: LoadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839) im .NET Security Blog.  

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie Assemblys aus Remotequellen geladen volles Vertrauen gewähren.

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>Siehe auch

- [Mehr impliziten verwendet der CAS-Richtlinie: LoadFromRemoteSources](https://go.microsoft.com/fwlink/p/?LinkId=266839)
- [Vorgehensweise: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
