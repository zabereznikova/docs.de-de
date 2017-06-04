---
title: "&lt;loadFromRemoteSources&gt;-Element | Microsoft Docs"
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
helpviewer_keywords: 
  - "loadFromRemoteSources-Element"
  - "<loadFromRemoteSources>-Element"
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
caps.latest.revision: 31
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 31
---
# &lt;loadFromRemoteSources&gt;-Element
Gibt an, ob Assemblys von Remotequellen volle Vertrauenswürdigkeit gewährt werden soll.  
  
> [!NOTE]
>  Wenn Sie zu diesem Thema wegen einer Fehlermeldung in der Visual Studio\-Projekt\-Fehlerliste oder eines Buildfehlers weitergeleitet wurden, finden Sie unter [Gewusst wie: Verwenden einer Assembly aus dem Internet in Visual Studio](http://msdn.microsoft.com/de-de/d8635b63-89a0-41aa-90f4-f351b2111070) Informationen.  
  
## Syntax  
  
```  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob eine aus Remotequellen geladene Assembly volle Vertrauenswürdigkeit gewährt werden soll.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Gewähren Sie Anwendungen aus Remotequellen keine vollständige Vertrauenswürdigkeit.  Dies ist der Standardwert.|  
|`true`|Gewähren Sie Anwendungen aus Remotequellen vollständige Vertrauenswürdigkeit.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## Hinweise  
 In .NET Framework 3.5 und früheren Versionen wurden Assemblys, die von einem Remotestandort geladen wurden, mit einem Berechtigungssatz als teilweise vertrauenswürdig ausgeführt, der von der Zone abhängig war, in der die Assembly geladen wurde.  Wenn Sie eine Assembly aus einer Website Arbeitsbereich, wurde sie in der Internetzone geladen und den Berechtigungssatz hat.  Die Ausführung ist mit anderen Worten in einer Internet\-Sandbox erfolgt.  Wenn Sie versuchen, diese Assembly in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] und höheren Versionen ausgeführt, wird eine Ausnahme ausgelöst; Sie müssen entweder einen Sandkasten für die Assembly nicht explizit erstellen \(siehe [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)\), oder führen Sie es in voller Vertrauenswürdigkeit aus.  
  
 Das `<loadFromRemoteSources>`\-Elements können Sie angeben, dass die Assemblys, die mit teilweiser Vertrauenswürdigkeit in früheren Versionen von .NET Framework ausgeführt hätten, sein, auf voll vertrauenswürdige in [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höheren Versionen sind.  Standardmäßig können die Assemblys nicht in [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höher.  Um eine Remoteanwendung Assembly auszuführen, müssen Sie sie entweder mit voller Vertrauenswürdigkeit ausführen oder einem Sandkasten <xref:System.AppDomain> erstellen im ihn ausführen.  
  
> [!NOTE]
>  In [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] werden Assemblys auf Freigaben des lokalen Netzwerks als standardmäßig volle Vertrauenswürdigkeit ausgeführt; Sie müssen das `<loadFromRemoteSources>`\-Element nicht aktivieren.  
  
> [!NOTE]
>  Wenn eine Anwendung aus dem Web kopiert wurde, wird durch Windows als Webanwendung bezeichnet, wenn sie auf dem lokalen Computer befinden.  Sie können diese Bezeichnung ändern, indem Sie die Dateieigenschaften ändern, oder Sie können der Assembly volle Vertrauenswürdigkeit mithilfe des `<loadFromRemoteSources>`\-Elements gewähren.  Alternativ können Sie die <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A>\-Methode verwenden, um eine lokale Assembly zu laden, die das Betriebssystem hat bezeichnet, z, Laden aus dem Web.  
  
 Das `enabled`\-Attribut für dieses Element ist nur wirksam, wenn die Codezugriffssicherheit \(CAS\) deaktiviert wird.  Die CAS\-Richtlinie ist in [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höher standardmäßig deaktiviert.  Wenn Sie `enabled` auf `true` festlegten, wird Remoteanwendungen volle Vertrauenswürdigkeit gewährt.  
  
 Wenn `<loadFromRemoteSources>` `enabled` nicht auf `true` festgelegt wird, wird unter folgenden Umständen eine Ausnahme ausgelöst:  
  
-   Das Sandboxverhalten der aktuellen Domäne unterscheidet sich vom Verhalten in [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  Dies erfordert eine Deaktivierung der CAS\-Richtlinie, und die aktuelle Domäne darf nicht Teil einer Sandbox sein.  
  
-   Die Assembly, die geladen wird, stammt nicht aus der `MyComputer`\-Zone.  
  
> [!NOTE]
>  Sie können eine <xref:System.IO.FileLoadException> in einer Windows Virtual PC\-Anwendung abrufen, wenn Sie versuchen, eine Datei aus verknüpften Ordnern auf dem Host\-Computer zu laden.  Dieser Fehler tritt möglicherweise auch auf, wenn Sie versuchen, eine Datei aus einem Ordner zu laden, der von [die Remotedesktopdienste](http://go.microsoft.com/fwlink/?LinkId=182775) verknüpft ist \(Terminaldienste\).  Um die Ausnahme zu vermeiden, setzen Sie das `enabled`\-Objekt auf `true`.  
  
 Sie können verhindern, dass diese Ausnahme ausgelöst wird, indem Sie das `<loadFromRemoteSources>`\-Element auf `true` festlegen.  Damit können Sie angeben, dass Sie sich nicht darauf verlassen, dass von der Common Language Runtime zur Sicherheit eine Sandbox für die geladenen Assemblys bereitgestellt wird und die Assemblys als vollständig vertrauenswürdig ausgeführt werden können.  
  
> [!IMPORTANT]
>  Legen Sie dieses Konfigurationselement nicht fest, wenn die Assembly nicht als vollständig vertrauenswürdig ausgeführt werden soll.  Erstellen Sie stattdessen eine Sandbox\-<xref:System.AppDomain>, in die die Assembly geladen werden soll.  
  
## Konfigurationsdatei  
 Dieses Element wird in der Regel in der Anwendungskonfigurationsdatei verwendet, kann jedoch in anderen Konfigurationsdateien je nach Kontext verwendet werden.  Weitere Informationen finden Sie im Artikel [Implizitere Verwendungen von CAS Richtlinien: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) im .NET\-Sicherheitsblog.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Anwendungen aus Remotequellen vollständige Vertrauenswürdigkeit gewährt wird.  
  
```  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Implizitere Verwendungen von CAS Richtlinien: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839)   
 [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)   
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)