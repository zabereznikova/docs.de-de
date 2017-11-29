---
title: 'Gewusst wie: Suchen von Assemblys mit DEVPATH'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DEVPATH
- .NET Framework application configuration, assemblies
- application configuration files, specifying assembly's location
- app.config files, assembly locations
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 44d2eadf-7eec-443c-a2ac-d601fd919e17
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 70448f7ce4c00274dde14bace603e5c8852bf148
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-locate-assemblies-by-using-devpath"></a>Gewusst wie: Suchen von Assemblys mit DEVPATH
Entwickler sollten sicherstellen, dass eine freigegebene Assembly, die sie erstellen mit mehreren Anwendungen ordnungsgemäß funktioniert. Anstatt kontinuierlich platzieren die Assembly im globalen Assemblycache während des Entwicklungszyklus, kann der Entwickler eine DEVPATH-Umgebungsvariable erstellen, die auf das Buildausgabeverzeichnis für die Assembly verweist.  
  
 Nehmen wir beispielsweise an, dass Sie beim Erstellen einer freigegebenen Assemblys mit dem Namen MySharedAssembly und das Ausgabeverzeichnis C:\MySharedAssembly\Debug. Sie können in der Variablen DEVPATH C:\MySharedAssembly\Debug einfügen. Sie müssen dann geben Sie die [ \<DevelopmentMode >](../../../docs/framework/configure-apps/file-schema/runtime/developmentmode-element.md) Element in der Computerkonfigurationsdatei. Dieses Element weist die common Language Runtime DEVPATH verwenden, um Assemblys zu suchen.  
  
 Die diese freigegebene Assembly muss von der Laufzeit erkannt werden.  Zum Angeben eines privaten Verzeichnisses zum Auflösen von Assembly Verweise verwenden die [ \<codeBase >-Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) oder [ \<probing > Element](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) in einer Konfigurationsdatei, wie in beschrieben [Angeben des Speicherortes einer Assembly](../../../docs/framework/configure-apps/specify-assembly-location.md).  Sie können auch die Assembly in einem Unterverzeichnis des Anwendungsverzeichnisses platziert. Weitere Informationen finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)(Seite möglicherweise auf Englisch).  
  
> [!NOTE]
>  Dies ist eine erweiterte Funktion, die nur für die Entwicklung vorgesehen.  
  
 Das folgende Beispiel veranschaulicht die dazu führen, dass die Common Language Runtime nach Assemblys die DEVPATH-Umgebungsvariable angegebenen Verzeichnisse suchen.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<configuration>  
  <runtime>  
    <developmentMode developerInstallation="true"/>  
  </runtime>  
</configuration>  
```  
  
 Diese Einstellung wird standardmäßig auf "false".  
  
> [!NOTE]
>  Verwenden Sie diese Einstellung nur zum Zeitpunkt der Entwicklung. Die Common Language Runtime überprüft nicht die Versionen auf Assemblys mit starkem Namen in die DEVPATH gefunden. Sie verwendet einfach die erste Assembly gefundenen.  
  
## <a name="see-also"></a>Siehe auch  
 [Konfigurieren von .NET Framework-Apps](http://msdn.microsoft.com/en-us/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
