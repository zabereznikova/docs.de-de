---
title: '&lt;LoadFromRemoteSources&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acd66cdff9f2c68e7d665b1fd236b18eeb9b4bac
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="ltloadfromremotesourcesgt-element"></a>&lt;LoadFromRemoteSources&gt; Element
Gibt an, ob Assemblys Remotedatenquellen volle Vertrauenswürdigkeit gewährt werden soll.  
  
> [!NOTE]
>  Wenn Sie eine Fehlermeldung in der Fehlerliste von Visual Studio-Projekt oder ein Buildfehler aufgrund von zu diesem Thema weitergeleitet wurden, finden Sie unter [Vorgehensweise: Verwenden Sie eine Assembly aus dem Internet in Visual Studio](http://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070).  
  
 \<configuration>  
\<Common Language Runtime >  
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
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob eine Assembly, die über Remotedatenquellen geladen wird volle Vertrauenswürdigkeit gewährt werden soll.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Gewähren Sie volle Vertrauenswürdigkeit nicht auf Anwendungen Remotedatenquellen. Dies ist die Standardeinstellung.|  
|`true`|Gewähren Sie volle Vertrauenswürdigkeit für Anwendungen Remotedatenquellen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 In .NET Framework, Version 3.5 und frühere Versionen müssen, wenn Sie von einem Remotestandort aus eine Assembly geladen würde die Assembly mit einem Berechtigungssatz teilweise vertrauenswürdigen ausgeführt werden, die die Zone abhängen, in denen es geladen wurde. Z. B. Wenn Sie von einer Website eine Assembly geladen, es wurde in der Internetzone geladen und den Internet-Berechtigungssatz gewährt. Das heißt, in der eine Internet-Sandkasten ausgeführt. Wenn Sie versuchen, diese Assembly auszuführen, der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] und höheren Versionen wird eine Ausnahme ausgelöst; Sie müssen entweder explizit einen Sandkasten für die Assembly erstellen (finden Sie unter [wie: Ausführen von teilweise vertrauenswürdigen Code in einem Sandkasten](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), oder vollständiger Vertrauenswürdigkeit ausgeführt.  
  
 Die `<loadFromRemoteSources>` Element können Sie angeben, dass die Assemblys, die teilweise vertrauenswürdige in frühere Versionen von .NET Framework ausgeführt worden wäre vollständig ausgeführt werden, die im vertrauenswürdig der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höheren Versionen. Standardmäßig remote Assemblys führen nicht in der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höher. Um eine remote-Assembly ausführen zu können, müssen Sie es als vollständig vertrauenswürdig ausführen oder Erstellen einer Sandbox <xref:System.AppDomain> in dem er ausgeführt.  
  
> [!NOTE]
>  In der [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], Assemblys auf der lokalen Netzwerkfreigaben werden standardmäßig mit voller Vertrauenswürdigkeit ausgeführt; Sie müssen nicht zum Aktivieren der `<loadFromRemoteSources>` Element.  
  
> [!NOTE]
>  Wenn eine Anwendung aus dem Web kopiert wurde, wird er von Windows gekennzeichnet als eine Web-Anwendung, auch wenn er auf dem lokalen Computer befindet. Sie können diese Bezeichnung durch Ändern der Dateieigenschaften ändern oder Sie können die `<loadFromRemoteSources>` Element, um die Assembly zu gewähren, volle Vertrauenswürdigkeit. Als Alternative können Sie die <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> Methode, um eine lokale Assembly zu laden, die das Betriebssystem gekennzeichnet wurde, als aus dem Web geladen wurde.  
  
 Die `enabled` Attribut für dieses Element wirksam ist, nur, wenn die Codezugriffssicherheit (CAS) deaktiviert ist. Standardmäßig ist die CAS-Richtlinie in deaktiviert die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höheren Versionen. Wenn Sie festlegen, `enabled` zu `true`, Remoteanwendungen volle Vertrauenswürdigkeit gewährt werden.  
  
 Wenn `<loadFromRemoteSources>` `enabled` nicht festgelegt ist, um `true`, in den folgenden Situationen wird eine Ausnahme ausgelöst:  
  
-   Das Verwenden einer Sandboxverhalten von der aktuellen Domäne unterscheidet sich vom Verhalten in der [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]. Dies erfordert CAS-Richtlinie deaktiviert werden soll, und der aktuellen Domäne Sandbox kann.  
  
-   Die geladene Assembly stammt nicht von der `MyComputer` Zone.  
  
> [!NOTE]
>  Sie erhalten möglicherweise eine <xref:System.IO.FileLoadException> in einer Windows Virtual PC-Anwendung, wenn Sie versuchen, eine Datei aus verknüpften Ordnern auf dem Hostcomputer zu laden. Dieser Fehler kann auch auftreten, wenn Sie versuchen, eine Datei aus einem Ordner, die über verknüpfte laden [Remote Desktop Services](http://go.microsoft.com/fwlink/?LinkId=182775) (Terminaldienste). Um die Ausnahme zu vermeiden, legen Sie `enabled` auf `true`.  
  
 Festlegen der `<loadFromRemoteSources>` Element `true` wird verhindert, dass diese Ausnahme ausgelöst wird. Können Sie angeben, dass Sie nicht auf die common Language Runtime für das Sandboxing geladenen Assemblys für die Sicherheit der vertrauenden Seite sind und dass sie erfolgen können, um die Ausführung als volle Vertrauenswürdigkeit.  
  
> [!IMPORTANT]
>  Wenn die Assembly nicht voller Vertrauenswürdigkeit ausgeführt werden soll, legen Sie dieses Element nicht. Erstellen Sie stattdessen eine Sandbox <xref:System.AppDomain> in dem die Assembly zu laden.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element wird in der Regel in der Anwendungskonfigurationsdatei verwendet, jedoch in andere Konfigurationsdateien, die je nach Kontext verwendet werden kann. Weitere Informationen finden Sie im Artikel [Weitere implizite verwendet der CAS-Richtlinie: LoadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) in .NET Security Blog.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie So gewähren Sie volle Vertrauenswürdigkeit für Anwendungen Remotedatenquellen wird.  
  
```xml  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Mehr impliziten Verwendungen von CAS-Richtlinie: LoadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839)  
 [How to: Run Partially Trusted Code in a Sandbox (Vorgehensweise: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten)](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
