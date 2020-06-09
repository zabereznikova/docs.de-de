---
title: 'Vorgehensweise: Verwenden von „Svcutil.exe“ zum Überprüfen von kompiliertem Dienstcode'
ms.date: 03/30/2017
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
ms.openlocfilehash: 6f2064c696e3186c3208a7e57dc51655056d23ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595348"
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a>Vorgehensweise: Verwenden von „Svcutil.exe“ zum Überprüfen von kompiliertem Dienstcode
Sie können das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) verwenden, um Fehler in Dienst Implementierungen und Konfigurationen zu erkennen, ohne den Dienst zu Hosting.  
  
### <a name="to-validate-a-service"></a>So überprüfen Sie einen Dienst  
  
1. Kompilieren Sie den Dienst in eine ausführbare Datei und eine oder mehrere abhängige Assemblys.  
  
2. Öffnen Sie eine SDK-Eingabeaufforderung.  
  
3. Starten Sie das Tool Svcutil.exe an der Eingabeaufforderung mit dem folgenden Format. Weitere Informationen zu den verschiedenen Parametern finden Sie im Abschnitt "Service validationsection" des Themas "Service [Model Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) ".  
  
    ```console
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     Sie müssen die `/serviceName`-Option verwenden, um den Konfigurationsnamen des Dienstes anzugeben, den Sie überprüfen möchten.  
  
     Das `assemblyPath`-Argument gibt den Pfad zur ausführbaren Datei für den Dienst und eine oder mehrere Assemblys an, die die zu überprüfenden Diensttypen enthalten. Die ausführbare Assembly muss über eine zugeordnete Konfigurationsdatei verfügen, um die Dienstkonfiguration bereitzustellen. Sie können standardmäßige Befehlszeilenplatzhalter verwenden, um mehrere Assemblys anzugeben.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl hat den Dienst myServiceName in der ausführbaren Datei myServiceHost.exe implementiert.  Die Konfigurationsdatei für den Dienst (myServiceHost.exe.config) wird automatisch geladen.  
  
```console  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
