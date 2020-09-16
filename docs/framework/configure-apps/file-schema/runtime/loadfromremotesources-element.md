---
title: <loadFromRemoteSources>-Element
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: 48da852bd1e209aed5ed5e75d8e510027a96d6d7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558008"
---
# <a name="loadfromremotesources-element"></a>\<loadFromRemoteSources>-Element
Gibt an, ob aus Remote Quellen geladene Assemblys in .NET Framework 4 und höher volle Vertrauenswürdigkeit gewährt werden sollen.
  
> [!NOTE]
> Wenn Sie aufgrund einer Fehlermeldung in der Visual Studio-Projekt Fehlerliste oder einem Buildfehler zu diesem Artikel weitergeleitet wurden, finden Sie weitere Informationen unter Gewusst [wie: Verwenden einer Assembly aus dem Web in Visual Studio](/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<loadFromRemoteSources>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob einer Assembly, die aus einer Remote Quelle geladen wird, volle Vertrauenswürdigkeit gewährt werden soll.|  
  
## <a name="enabled-attribute"></a>aktiviertes Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|`false`|Gewähren Sie Anwendungen aus Remote Quellen keine volle Vertrauenswürdigkeit. Dies ist die Standardoption.|  
|`true`|Gewähren Sie Anwendungen aus Remote Quellen volle Vertrauenswürdigkeit.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise

Wenn Sie in der .NET Framework 3,5 und früheren Versionen eine Assembly von einem Remote Speicherort laden, wird der Code in der Assembly mit teilweiser Vertrauenswürdigkeit mit einem Berechtigungs Satz ausgeführt, der von der Zone abhängig ist, aus der er geladen wurde. Wenn Sie z. b. eine Assembly von einer Website laden, wird Sie in die Internet Zone geladen und erhält den Internet Berechtigungs Satz. Das heißt, Sie wird in einer Internet Sandbox ausgeführt.

Ab .NET Framework 4 ist die Richtlinie für die Code Zugriffssicherheit (Code Access Security, CAS) deaktiviert, und Assemblys werden mit voller Vertrauenswürdigkeit geladen. Normalerweise würde dies Assemblys, die mit der Methode geladen werden <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> , die zuvor Sandkasten waren, vollständig Vertrauen gewähren. Um dies zu verhindern, ist die Möglichkeit, Code in aus einer Remote Quelle geladenen Assemblys auszuführen, standardmäßig deaktiviert. Wenn Sie versuchen, eine Remoteassembly zu laden, wird standardmäßig eine <xref:System.IO.FileLoadException> mit einer Ausnahme Meldung wie die folgende ausgelöst:

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

Um die Assembly zu laden und Ihren Code auszuführen, müssen Sie eine der folgenden Aktionen ausführen:

- Erstellen Sie explizit eine Sandbox für die Assembly (Weitere Informationen finden [Sie unter Gewusst wie: Ausführen von teilweise vertrauenswürdigem Code in einer Sandbox](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)).

- Führen Sie den Assemblycode in voller Vertrauenswürdigkeit aus. Dazu konfigurieren Sie das- `<loadFromRemoteSources>` Element. Mit dieser Einstellung können Sie angeben, dass die Assemblys, die in früheren Versionen des .NET Framework in teilweiser Vertrauenswürdigkeit ausgeführt werden, nun in der .NET Framework 4 und höheren Versionen mit voller Vertrauenswürdigkeit ausgeführt werden

> [!IMPORTANT]
> Wenn die Assembly nicht mit voller Vertrauenswürdigkeit ausgeführt werden soll, legen Sie dieses Konfigurationselement nicht fest. Erstellen Sie stattdessen einen Sandkasten, <xref:System.AppDomain> in dem die Assembly geladen werden soll.

Das- `enabled` Attribut für das- `<loadFromRemoteSources>` Element ist nur wirksam, wenn Code Zugriffssicherheit (Code Access Security, CAS) deaktiviert ist. Standardmäßig ist die CAS-Richtlinie in den .NET Framework 4 und höheren Versionen deaktiviert. Wenn Sie auf festlegen, wird für Remoteassemblys `enabled` `true` volle Vertrauenswürdigkeit gewährt.

Wenn `enabled` nicht auf festgelegt ist `true` , <xref:System.IO.FileLoadException> wird eine unter den folgenden Bedingungen ausgelöst:

- Das Sandkasten Verhalten der aktuellen Domäne unterscheidet sich vom Verhalten in der .NET Framework 3,5. Hierfür muss die CAS-Richtlinie deaktiviert werden, und die aktuelle Domäne darf nicht als Sandkasten angezeigt werden.

- Die Assembly, die geladen wird, befindet sich nicht in der `MyComputer` Zone.

Durch Festlegen des- `<loadFromRemoteSources>` Elements auf `true` wird verhindert, dass diese Ausnahme ausgelöst wird. Sie können angeben, dass Sie sich nicht auf den Common Language Runtime verlassen, um die geladenen Assemblys auf die Sicherheit zu überführen, und dass Sie in voller Vertrauenswürdigkeit ausgeführt werden können.

## <a name="notes"></a>Hinweise

- In den .NET Framework 4,5 und höheren Versionen werden Assemblys auf lokalen Netzwerkfreigaben standardmäßig mit vollständiger Vertrauenswürdigkeit ausgeführt. Sie müssen das-Element nicht aktivieren `<loadFromRemoteSources>` .

- Wenn eine Anwendung aus dem Web kopiert wurde, wird Sie von Windows als Webanwendung gekennzeichnet, auch wenn Sie sich auf dem lokalen Computer befindet. Sie können diese Bezeichnung ändern, indem Sie Ihre Dateieigenschaften ändern, oder Sie können das-Element verwenden, `<loadFromRemoteSources>` um der Assembly volle Vertrauenswürdigkeit zu gewähren. Als Alternative können Sie die-Methode verwenden, <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> um eine lokale Assembly zu laden, die vom Betriebssystem als aus dem Web geladen wurde.

- Sie erhalten möglicherweise eine <xref:System.IO.FileLoadException> in einer Anwendung, die in einer Windows Virtual PC-Anwendung ausgeführt wird. Dies kann vorkommen, wenn Sie versuchen, eine Datei aus verknüpften Ordnern auf dem hostingcomputer zu laden. Dies kann auch auftreten, wenn Sie versuchen, eine Datei aus einem Ordner zu laden, der über [Remotedesktopdienste](/windows/win32/termserv/terminal-services-portal) (Terminal Dienste) verknüpft ist. Um die Ausnahme zu vermeiden, legen `enabled` Sie auf fest `true` .

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element wird in der Regel in der Anwendungs Konfigurationsdatei verwendet, kann aber in anderen Konfigurationsdateien verwendet werden, je nach Kontext. Weitere Informationen finden Sie im Artikel zur [impliziten Verwendung der CAS-Richtlinie: loadFromRemoteSources](/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) im .net Security-Blog.  

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie Assemblys, die aus Remote Quellen geladen werden, volle Vertrauenswürdigkeit gewähren

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>Siehe auch

- [Implizitere Verwendung der CAS-Richtlinie: loadFromRemoteSources](/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [How to: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Lauf Zeit Einstellungs Schema](index.md)
- [Konfigurationsdateischema](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
