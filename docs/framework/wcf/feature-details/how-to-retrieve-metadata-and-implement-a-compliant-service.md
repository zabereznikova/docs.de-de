---
title: 'Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts'
ms.date: 03/30/2017
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
ms.openlocfilehash: 92d1549bfaf1f08c4e4200b5305aa130fdfc152c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276047"
---
# <a name="how-to-retrieve-metadata-and-implement-a-compliant-service"></a>Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts

Oftmals werden Dienste nicht von derselben Person entworfen und anschließend implementiert. In Umgebungen, in denen zusammenwirkende Anwendungen wichtig sind, können Verträge in Web Services Description Language (WSDL) entworfen oder beschrieben werden, und ein Entwickler muss einen Dienst implementieren, der mit dem bereitgestellten Vertrag kompatibel ist. Möglicherweise möchten Sie auch einen vorhandenen Dienst zu Windows Communication Foundation (WCF) migrieren, behalten jedoch das Wire-Format bei. Außerdem werden Aufrufende von Duplexverträgen dazu aufgefordert, auch einen Rückrufvertrag zu implementieren.  
  
 In diesen Fällen müssen Sie das Service [Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) (oder ein entsprechendes Tool) verwenden, um eine Dienstvertrags Schnittstelle in einer verwalteten Sprache zu generieren, die Sie implementieren können, um die Anforderungen des Vertrags zu erfüllen. In der Regel wird das [Service Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) zum Abrufen eines Dienstvertrags verwendet, der für eine Kanalfactory oder einen WCF-Clienttyp verwendet wird, sowie eine Client Konfigurationsdatei, mit der die richtige Bindung und Adresse eingerichtet werden. Um die generierte Konfigurationsdatei zu verwenden, müssen Sie diese in eine Dienstkonfigurationsdatei ändern. Sie müssen möglicherweise auch den Dienstvertrag ändern.  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a>So rufen Sie Daten ab und implementieren einen kompatiblen Dienst:  
  
1. Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) für Metadatendateien oder einen Metadatenendpunkt, um eine Codedatei zu generieren.  
  
2. Suchen Sie den Bereich der Ausgabecodedatei mit der wichtigen Schnittstelle (falls mehr als eine vorhanden ist), die mit dem <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>-Attribut gekennzeichnet ist. Das folgende Codebeispiel zeigt die beiden Schnittstellen, die vom [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)generiert werden. Die erste Schnittstelle (`ISampleService`) ist die Dienstvertragsschnittstelle, die zum Erstellen eines kompatiblen Diensts implementiert wird. Bei der zweiten Schnittstelle (`ISampleServiceChannel`) handelt es sich um eine Hilfsschnittstelle für die Clientverwendung, die sowohl die Dienstvertragsschnittstelle als auch <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> erweitert und für die Verwendung in einer Clientanwendung vorgesehen ist.  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3. Wird mit WSDL keine Antwortaktion für alle Vorgänge angegeben, ist bei den generierten Vorgangsverträgen die <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A>-Eigenschaft möglicherweise auf das Platzhalterzeichen (*) festgelegt. Entfernen Sie diese Eigenschafteneinstellung. Andernfalls können die Metadaten bei der Implementierung der Dienstvertragsmetadaten nicht für diese Vorgänge exportiert werden.  
  
4. Implementieren Sie die Schnittstelle in einer Klasse, und hosten Sie den Dienst. Ein Beispiel finden Sie unter Gewusst [wie: Implementieren eines Dienstvertrags](../how-to-implement-a-wcf-contract.md), oder eine einfache Implementierung finden Sie unten im Abschnitt "Beispiel".  
  
5. Ändern Sie in der Client Konfigurationsdatei, die das [Service Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) generiert, den [\<client>](../../configure-apps/file-schema/wcf/client.md) Konfigurations Abschnitt in einen [\<services>](../../configure-apps/file-schema/wcf/services.md) Konfigurations Abschnitt. (Ein Beispiel für eine generierte Clientanwendungs-Konfigurationsdatei finden Sie im folgenden "Beispiel"-Abschnitt.)  
  
6. [\<services>](../../configure-apps/file-schema/wcf/services.md)Erstellen Sie im Konfigurations Abschnitt ein- `name` Attribut im [\<services>](../../configure-apps/file-schema/wcf/services.md) Konfigurations Abschnitt für die Dienst Implementierung.  
  
7. Legen Sie das `name`-Dienstattribut auf den Konfigurationsnamen für die Dienstimplementierung fest.  
  
8. Fügen Sie die Endpunktkonfigurationselemente hinzu, die den implementierten Dienstvertrag für den Dienstkonfigurationsabschnitt verwenden.  
  
## <a name="example"></a>Beispiel  

 Das folgende Codebeispiel zeigt den Großteil einer Codedatei, die durch Ausführen des [Service Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) für Metadatendateien generiert wird.  
  
 Dies wird im folgenden Code veranschaulicht:  
  
- Die Dienstvertragsschnittstelle (`ISampleService`), die bei der Implementierung den Vertragsanforderungen entspricht.  
  
- Die Hilfsschnittstelle für die Clientverwendung, die sowohl die Dienstvertragsschnittstelle als auch <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> erweitert und für die Verwendung in einer Clientanwendung (`ISampleServiceChannel`) vorgesehen ist.  
  
- Die Hilfsklasse, die <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> erweitert und für die Verwendung in einer Clientanwendung (`SampleServiceClient`) vorgesehen ist.  
  
- Die vom Dienst generierte Konfigurationsdatei.  
  
- Eine einfache `ISampleService`-Dienstimplementierung.  
  
- Eine Konvertierung der clientseitigen Konfigurationsdatei in eine dienstseitige Version.  
  
[!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]

[!code-xml[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]

[!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]

[!code-xml[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]
  
## <a name="see-also"></a>Weitere Informationen

- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
