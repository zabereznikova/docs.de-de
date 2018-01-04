---
title: "Vorgehensweise: Verwenden von \"Svcutil.exe\" zum Überprüfen von kompiliertem Dienstcode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b60356bd66a49c9599a8e0a9138d3b92dbe0b23c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a>Vorgehensweise: Verwenden von "Svcutil.exe" zum Überprüfen von kompiliertem Dienstcode
Sie können die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Erkennen von Fehlern in dienstimplementierungen und Konfigurationen, ohne den Dienst hostet.  
  
### <a name="to-validate-a-service"></a>So überprüfen Sie einen Dienst  
  
1.  Kompilieren Sie den Dienst in eine ausführbare Datei und eine oder mehrere abhängige Assemblys.  
  
2.  Öffnen Sie eine SDK-Eingabeaufforderung.  
  
3.  Starten Sie das Tool Svcutil.exe an der Eingabeaufforderung mit dem folgenden Format. Weitere Informationen zu den verschiedenen Parametern finden Sie unter der Validationsection-Dienst, der die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Thema.  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     Sie müssen die `/serviceName`-Option verwenden, um den Konfigurationsnamen des Dienstes anzugeben, den Sie überprüfen möchten.  
  
     Das `assemblyPath`-Argument gibt den Pfad zur ausführbaren Datei für den Dienst und eine oder mehrere Assemblys an, die die zu überprüfenden Diensttypen enthalten. Die ausführbare Assembly muss über eine zugeordnete Konfigurationsdatei verfügen, um die Dienstkonfiguration bereitzustellen. Sie können standardmäßige Befehlszeilenplatzhalter verwenden, um mehrere Assemblys anzugeben.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl hat den Dienst myServiceName in der ausführbaren Datei myServiceHost.exe implementiert.  Die Konfigurationsdatei für den Dienst (myServiceHost.exe.config) wird automatisch geladen.  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a>Siehe auch  
 [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
