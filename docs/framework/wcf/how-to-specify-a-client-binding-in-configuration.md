---
title: 'Vorgehensweise: Angeben einer Clientbindung in einer Konfiguration'
description: Erfahren Sie, wie Sie die Bindung für einen WCF-Client deklarativ in einer Konfigurationsdatei angeben können. Der Client greift in diesem Beispiel auf einen Dienst zu.
ms.date: 03/30/2017
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
ms.openlocfilehash: e8a552211b28c1323b2afd595c5b060db6b2824a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236506"
---
# <a name="how-to-specify-a-client-binding-in-configuration"></a>Vorgehensweise: Angeben einer Clientbindung in einer Konfiguration

In diesem Beispiel wird eine Client-Konsolenanwendung erstellt, um einen Rechnerdienst zu nutzen, und die Bindung dieses Clients wird deklarativ in der Konfiguration angegeben. Der Client greift auf den `CalculatorService` zu, der die `ICalculator`-Schnittstelle implementiert, und sowohl der Dienst als auch der Client verwenden die Klasse <xref:System.ServiceModel.BasicHttpBinding>.  
  
 In der umrissenen Prozedur wird davon ausgegangen, dass der Rechnerdienst ausgeführt wird. Weitere Informationen zum Erstellen des Dienstanbieter finden Sie unter Gewusst [wie: Angeben einer Dienst Bindung in der Konfiguration](how-to-specify-a-service-binding-in-configuration.md). Außerdem wird das [Service Model Metadata Utility-Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) verwendet, das Windows Communication Foundation (WCF) bereitstellt, um die Client Komponenten automatisch zu generieren. Das Tool generiert den Clientcode und die Konfiguration zum Zugreifen auf den Dienst.  
  
 Der Client wird in zwei Schritten erstellt. Svcutil.exe generiert den `ClientCalculator`, der die `ICalculator`-Schnittstelle implementiert. Diese Clientanwendung wird dann durch das Erstellen einer Instanz von `ClientCalculator` erstellt.  
  
 Normalerweise ist es die bewährte Methode, die Bindung anzugeben und die Informationen deklarativ in der Konfiguration anzusprechen anstatt imperativ im Code. Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden. Allgemeiner gesagt ist es durch die Trennung von Bindungs- und Adressierungsinformationen vom Code möglich, diese zu ändern, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.  
  
 Mit dem [Konfigurations-Editor-Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md)können Sie alle folgenden Konfigurationsschritte ausführen.  
  
 Die Quell Kopie dieses Beispiels finden Sie im Beispiel " [BasicBinding](./samples/basicbinding.md) ".  
  
### <a name="specifying-a-client-binding-in-configuration"></a>Eine Clientbindung in einer Konfiguration angeben  
  
1. Verwenden Sie Svcutil.exe in der Befehlszeile, um Code von Dienstmetadaten zu generieren.  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. Der generierte Client enthält die `ICalculator`-Schnittstelle, die den Dienstvertrag definiert, dem die Clientimplementierung entsprechen muss.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3. Der generierte Client enthält außerdem die Implementierung vom `ClientCalculator`.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4. Svcutil.exe generiert auch die Konfiguration für den Client, der die <xref:System.ServiceModel.BasicHttpBinding>-Klasse verwendet. Wenn Sie Visual Studio verwenden, benennen Sie diese Datei App.config. Beachten Sie, dass die Adress-und Bindungs Informationen nicht an einer beliebigen Stelle in der Implementierung des Dienstanbieter angegeben werden. Es muss auch kein Code geschrieben werden, um Informationen aus der Konfigurationsdatei abzurufen.  
  
     [!code-xml[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]

5. Erstellen Sie eine Instanz des `ClientCalculator` in einer Anwendung, und rufen Sie dann die Dienstvorgänge auf.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6. Kompilieren Sie den Code, und führen Sie den Client aus.  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](using-bindings-to-configure-services-and-clients.md)
