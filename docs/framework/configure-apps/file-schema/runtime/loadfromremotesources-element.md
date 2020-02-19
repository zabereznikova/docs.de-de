---
title: <loadFromRemoteSources>-Element
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: 454314bf1002a9648f669cc708c8ac42461fccaf
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452265"
---
# <a name="loadfromremotesources-element"></a>\<loadFromRemoteSources-> Element
Gibt an, ob aus Remote Quellen geladene Assemblys in .NET Framework 4 und höher volle Vertrauenswürdigkeit gewährt werden sollen.
  
> [!NOTE]
> Wenn Sie aufgrund einer Fehlermeldung in der Visual Studio-Projekt Fehlerliste oder einem Buildfehler zu diesem Artikel weitergeleitet wurden, finden Sie weitere Informationen unter Gewusst [wie: Verwenden einer Assembly aus dem Web in Visual Studio](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100)).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<loadFromRemoteSources >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente
 In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob einer Assembly, die aus einer Remote Quelle geladen wird, volle Vertrauenswürdigkeit gewährt werden soll.|  
  
## <a name="enabled-attribute"></a>aktiviertes Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Gewähren Sie Anwendungen aus Remote Quellen keine volle Vertrauenswürdigkeit. Dies ist die Standardoption.|  
|`true`|Gewähren Sie Anwendungen aus Remote Quellen volle Vertrauenswürdigkeit.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise

Wenn Sie in der .NET Framework 3,5 und früheren Versionen eine Assembly von einem Remote Speicherort laden, wird der Code in der Assembly mit teilweiser Vertrauenswürdigkeit mit einem Berechtigungs Satz ausgeführt, der von der Zone abhängig ist, aus der er geladen wurde. Wenn Sie z. b. eine Assembly von einer Website laden, wird Sie in die Internet Zone geladen und erhält den Internet Berechtigungs Satz. Das heißt, Sie wird in einer Internet Sandbox ausgeführt.

Ab .NET Framework 4 ist die Richtlinie für die Code Zugriffssicherheit (Code Access Security, CAS) deaktiviert, und Assemblys werden mit voller Vertrauenswürdigkeit geladen. Normalerweise würde dadurch eine volle Vertrauenswürdigkeit für Assemblys gewährt werden, die mit der <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>-Methode geladen werden, die zuvor in einem Sandkasten Um dies zu verhindern, ist die Möglichkeit, Code in aus einer Remote Quelle geladenen Assemblys auszuführen, standardmäßig deaktiviert. Wenn Sie versuchen, eine Remoteassembly zu laden, wird standardmäßig eine <xref:System.IO.FileLoadException> mit einer Ausnahme Meldung wie der folgenden ausgelöst:

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

- Führen Sie den Assemblycode in voller Vertrauenswürdigkeit aus. Dazu konfigurieren Sie das `<loadFromRemoteSources>`-Element. Mit dieser Einstellung können Sie angeben, dass die Assemblys, die in früheren Versionen des .NET Framework in teilweiser Vertrauenswürdigkeit ausgeführt werden, nun in der .NET Framework 4 und höheren Versionen mit voller Vertrauenswürdigkeit ausgeführt werden

> [!IMPORTANT]
> Wenn die Assembly nicht mit voller Vertrauenswürdigkeit ausgeführt werden soll, legen Sie dieses Konfigurationselement nicht fest. Erstellen Sie stattdessen einen Sandkasten <xref:System.AppDomain>, in dem die Assembly geladen werden soll.

Das `enabled`-Attribut für das `<loadFromRemoteSources>`-Element ist nur wirksam, wenn die Code Zugriffssicherheit (Code Access Security, CAS) deaktiviert ist. Standardmäßig ist die CAS-Richtlinie in den .NET Framework 4 und höheren Versionen deaktiviert. Wenn Sie `enabled` auf `true`festlegen, wird Remoteassemblys volle Vertrauenswürdigkeit gewährt.

Wenn `enabled` nicht auf `true`festgelegt ist, wird unter den folgenden Bedingungen eine <xref:System.IO.FileLoadException> ausgelöst:

- Das Sandkasten Verhalten der aktuellen Domäne unterscheidet sich vom Verhalten in der .NET Framework 3,5. Hierfür muss die CAS-Richtlinie deaktiviert werden, und die aktuelle Domäne darf nicht als Sandkasten angezeigt werden.

- Die Assembly, die geladen wird, befindet sich nicht aus der `MyComputer` Zone.

Wenn Sie das `<loadFromRemoteSources>`-Element auf `true` festlegen, wird verhindert, dass diese Ausnahme ausgelöst wird. Sie können angeben, dass Sie sich nicht auf den Common Language Runtime verlassen, um die geladenen Assemblys auf die Sicherheit zu überführen, und dass Sie in voller Vertrauenswürdigkeit ausgeführt werden können.

## <a name="notes"></a>Hinweise

- In den .NET Framework 4,5 und höheren Versionen werden Assemblys auf lokalen Netzwerkfreigaben standardmäßig mit vollständiger Vertrauenswürdigkeit ausgeführt. Sie müssen das `<loadFromRemoteSources>`-Element nicht aktivieren.

- Wenn eine Anwendung aus dem Web kopiert wurde, wird Sie von Windows als Webanwendung gekennzeichnet, auch wenn Sie sich auf dem lokalen Computer befindet. Sie können diese Bezeichnung ändern, indem Sie Ihre Dateieigenschaften ändern, oder Sie können das `<loadFromRemoteSources>`-Element verwenden, um der Assembly volle Vertrauenswürdigkeit zu gewähren. Als Alternative können Sie die <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A>-Methode verwenden, um eine lokale Assembly zu laden, die vom Betriebssystem als aus dem Web geladen wurde.

- Sie erhalten möglicherweise eine <xref:System.IO.FileLoadException> in einer Anwendung, die in einer Windows Virtual PC-Anwendung ausgeführt wird. Dies kann vorkommen, wenn Sie versuchen, eine Datei aus verknüpften Ordnern auf dem hostingcomputer zu laden. Dies kann auch auftreten, wenn Sie versuchen, eine Datei aus einem Ordner zu laden, der über [Remotedesktopdienste](/windows/win32/termserv/terminal-services-portal) (Terminal Dienste) verknüpft ist. Um die Ausnahme zu vermeiden, legen Sie `enabled` auf `true`fest.

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element wird in der Regel in der Anwendungs Konfigurationsdatei verwendet, kann aber in anderen Konfigurationsdateien verwendet werden, je nach Kontext. Weitere Informationen finden Sie im Artikel zur [impliziten Verwendung der CAS-Richtlinie: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources) im .net Security-Blog.  

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

- [Implizitere Verwendung der CAS-Richtlinie: loadFromRemoteSources](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [How to: Run Partially Trusted Code in a Sandbox (Vorgehensweise: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten)](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>
