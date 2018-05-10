---
title: Angeben und Behandeln von Fehlern in Verträgen und Diensten
ms.date: 03/30/2017
helpviewer_keywords:
- handling faults [WCF]
ms.assetid: a9696563-d404-4905-942d-1e0834c26dea
ms.openlocfilehash: 93ebbf3410dc197982ca617b4e989d07f0e0b454
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="specifying-and-handling-faults-in-contracts-and-services"></a>Angeben und Behandeln von Fehlern in Verträgen und Diensten
Windows Communication Foundation (WCF)-Anwendungen behandeln Fehler durch verwaltete Ausnahmeobjekte SOAP-Fehlerobjekten und SOAP-Fehlerobjekte verwalteten Ausnahmeobjekten zuordnen. Die Themen in diesem Abschnitt erläutern, wie Verträge erstellt werden, die Fehlerbedingungen als benutzerdefinierte SOAP-Fehler verfügbar machen, wie solche Fehler als Teil einer Dienstimplementierung zurückgegeben werden, und wie Clients diese Fehler abfangen.  
  
## <a name="error-handling-overview"></a>Übersicht über die Fehlerbehandlung  
 In allen verwalteten Anwendungen werden Verarbeitungsfehler durch <xref:System.Exception>-Objekte dargestellt. In SOAP-basierten Anwendungen wie z. B. WCF-Anwendungen kommunizieren Dienstmethoden Verarbeitung Fehlerinformationen mit SOAP-Fehlernachrichten. SOAP-Fehler sind Nachrichtentypen, die in den Metadaten für einen Dienstvorgang enthalten sind und daher einen Fehlervertrag erstellen, den Clients nutzen können, um ihre Ausführung robuster oder interaktiver zu gestalten. Da SOAP-Fehler gegenüber Clients in XML-Form ausgedrückt werden, ist es darüber hinaus ein sehr interoperables Typsystem, das auf jeder Plattform SOAP-Clients erhöhen die Reichweite Ihrer WCF-Anwendung verwenden können, an.  
  
 Da WCF-Anwendungen unter beiden fehlersystemtypen ausgeführt werden, muss Informationen zu verwalteten Ausnahmen, die an den Client gesendet werden werden von Ausnahmen in SOAP-Fehler für den Dienst konvertiert, gesendet und fehlerausnahmen in WCF-Clients aus SOAP-Fehler konvertiert. Im Fall von Duplexclients können Clientverträge SOAP-Fehler auch zurück an einen Dienst senden. In beiden Fällen können Sie die Standard-Dienstausnahmeverhalten verwenden oder aber ausdrücklich steuern, ob und wie Ausnahmen Fehlernachrichten zugeordnet werden.  
  
 Zwei Typen von SOAP-Fehler gesendet werden können: *deklariert* und *nicht deklarierte*. Deklarierte SOAP-Fehler sind jene, bei denen ein Vorgang über ein <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>-Attribut verfügt, das einen benutzerdefinierten SOAP-Fehlertyp angibt. *Nicht deklarierte* SOAP-Fehler sind nicht im Vertrag für einen Vorgang angegeben.  
  
 Es wird dringend empfohlen, dass Dienstvorgänge ihre Fehler mithilfe des <xref:System.ServiceModel.FaultContractAttribute>-Attributs deklarieren, um alle SOAP-Fehler formal anzugeben, die bei einem Client während des normalen Betriebs eingehen können. Es wird außerdem empfohlen, dass in einem SOAP-Fehler nur die Informationen zurückgegeben werden, die ein Client erhalten muss, um die Offenlegung von Informationen möglichst gering zu halten.  
  
 In der Regel führen Dienste (und Duplexclients) die folgenden Schritte aus, um die Fehlerbehandlung erfolgreich in ihre Anwendungen zu integrieren:  
  
-   Sie ordnen Ausnahmebedingungen benutzerdefinierten SOAP-Fehlern zu.  
  
-   Clients und Dienste senden und empfangen SOAP-Fehler als Ausnahmen.  
  
 Darüber hinaus können WCF-Clients und Dienste nicht deklarierte SOAP-Fehler für Debugzwecke und standardmäßiges Fehlerverhalten erweitern können. Diese Aufgaben und Begriffe werden in den folgenden Abschnitten erläutert.  
  
## <a name="map-exceptions-to-soap-faults"></a>Zuordnen von Ausnahmen zu SOAP-Fehlern  
 Der erste Schritt bei der Definition eines Verfahrens zur Behandlung von Fehlerbedingungen besteht darin zu entscheiden, unter welchen Bedingungen eine Clientanwendung über Fehler informiert werden sollte. Die Fehlerbedingungen mancher Vorgänge werden von ihrer Funktionalität bestimmt. Ein `PurchaseOrder`-Vorgang könnte z.&#160;B. bestimmte Informationen an Kunden zurückgeben, denen es nicht mehr erlaubt ist, eine Bestellung zu tätigen. In anderen Fällen, etwa einem `Calculator`-Dienst, könnte ein allgemeinerer `MathFault`-SOAP-Fehler ausreichen, um alle Fehlerbedingungen für den gesamten Dienst zu beschreiben. Nachdem die Fehlerbedingungen der Clients Ihres Diensts identifiziert wurden, kann ein benutzerdefinierter SOAP-Fehler erstellt und der Vorgang dafür gekennzeichnet werden, dass er den SOAP-Fehler zurückgibt, wenn die entsprechende Fehlerbedingung eintritt.  
  
 Weitere Informationen zu diesem Schritt von dem Dienst oder Client entwickeln, finden Sie unter [definieren und Angeben von Fehlern](../../../docs/framework/wcf/defining-and-specifying-faults.md).  
  
## <a name="clients-and-services-handle-soap-faults-as-exceptions"></a>Clients und Dienste behandeln SOAP-Fehler als Ausnahmen  
 Identifizierung von fehlerbedingungen bei Vorgängen, benutzerdefinierter SOAP-Fehler und die Markierung dieser Vorgänge Rückgabe solcher Fehler sind die ersten Schritte erfolgreichen Fehlerbehandlung in WCF-Anwendungen. Der nächste Schritt besteht darin, das Senden und Empfangen dieser Fehler korrekt zu implementieren. In der Regel werden Fehler von Diensten gesendet, um ihre Clientanwendungen über Fehlerbedingungen zu informieren. Duplexclients können jedoch selbst auch SOAP-Fehler an Dienste senden.  
  
 Weitere Informationen finden Sie unter [senden und Empfangen von Fehlern](../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
## <a name="undeclared-soap-faults-and-debugging"></a>Undeklarierte SOAP-Fehler und Debuggen  
 Deklarierte SOAP-Fehler sind äußerst nützlich zur Erstellung interoperabler, verteilter Anwendungen. In manchen Fällen ist es jedoch für einen Dienst (oder einen Duplexclient) nützlich, einen undeklarierten SOAP-Fehler zu senden, also einen, der in der Web Services Description Language (WSDL) für diesen Vorgang nicht erwähnt ist. Bei der Entwicklung eines Diensts können beispielsweise unerwartete Situationen eintreten, in denen es für Debuggingzwecke sinnvoll sein kann, Information an den Client zurückzusenden. Darüber hinaus können Sie festlegen der <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> Eigenschaft oder die <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> Eigenschaft `true` gestatten WCF-Clients Informationen über interne dienstvorgangsausnahmen abzurufen. Senden von Fehlern einzelner sowohl die Debugeigenschaften Verhalten festlegen, werden beschrieben [senden und Empfangen von Fehlern](../../../docs/framework/wcf/sending-and-receiving-faults.md).  
  
> [!IMPORTANT]
>  Da mit verwaltete Ausnahmen interne Anwendungsinformationen verfügbar machen können, der Festlegung <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> oder <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> auf `true` ermöglicht WCF-Clients zum Abrufen von Informationen über interne dienstvorgangsausnahmen, einschließlich persönlich identifizierbarer oder anderer vertraulicher Informationen.  
>   
>  Daher wird die Festlegung von <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> oder <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> auf `true` nur für das vorübergehende Debuggen einer Dienstanwendung empfohlen. Außerdem beinhaltet die WSDL für eine Methode, die nicht behandelte verwaltete Ausnahmen auf diese Weise zurückgibt, keinen Vertrag für die <xref:System.ServiceModel.FaultException%601> vom Typ <xref:System.ServiceModel.ExceptionDetail>. Clients müssen erwarten, dass die Möglichkeit, einen unbekannten SOAP-Fehler (für WCF-Clients als zurückgegeben <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> Objekte), die Debuginformationen korrekt abrufen.  
  
## <a name="customizing-error-handling-with-ierrorhandler"></a>Anpassen der Fehlerbehandlung mit IErrorHandler  
 Wenn Sie spezielle Anforderungen bei der Anpassung der Antwortnachricht für den Client im Fall einer Ausnahme auf Anwendungsebene erfüllen oder spezielle Verarbeitungsschritte ausführen müssen, nachdem eine Antwortnachricht zurückgegeben wurde, dann implementieren Sie die <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=nameWithType>-Schnittstelle.  
  
## <a name="fault-serialization-issues"></a>Probleme bei der Fehlerserialisierung  
 Beim Deserialisieren eines Fehlervertrags versucht WCF zunächst, den Namen des Fehlervertrags in der SOAP-Nachricht einem Fehlervertragstyp zuzuordnen. Wenn keine exakte Übereinstimmung gefunden werden kann, wird die Liste der verfügbaren Fehlerverträge in alphabetischer Reihenfolge nach einem kompatiblen Typ durchsucht. Wenn zwei Fehlerverträge kompatible Typen darstellen (beispielsweise ist einer die Unterklasse eines anderen), wird möglicherweise der falsche Typ zum Deserialisieren des Fehlers verwendet. Dies geschieht nur, wenn im Fehlervertrag nicht sowohl Name, als auch Namespace und Aktion angegeben wurden. Um dieses Problem zu vermeiden, sollten Fehlerverträge daher stets durch Angabe von Attributen für Name, Namespace und Aktion vollständig qualifiziert werden. Darüber hinaus muss bei verwandten Fehlerverträgen, die von einer freigegebenen Basisklasse abgeleitet wurden, sichergestellt werden, dass neue Member mit `[DataMember(IsRequired=true)]` gekennzeichnet werden. Weitere Informationen über das `IsRequired`-Attribut finden Sie unter <xref:System.Runtime.Serialization.DataMemberAttribute>. Dadurch wird verhindert, dass ein kompatibler Typ als Basisklasse verwendet wird, und die Deserialisierung des Fehlers in den richtigen abgeleiteten Typ wird erzwungen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.FaultException>  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.ServiceModel.FaultException>  
 <xref:System.Xml.Serialization.XmlSerializer>  
 <xref:System.ServiceModel.XmlSerializerFormatAttribute>  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.ServiceModel.CommunicationException>  
 <xref:System.ServiceModel.FaultContractAttribute.Action%2A>  
 <xref:System.ServiceModel.FaultException.Code%2A>  
 <xref:System.ServiceModel.FaultException.Reason%2A>  
 <xref:System.ServiceModel.FaultCode.SubCode%2A>  
 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>  
 [Definieren und Angeben von Fehlern](../../../docs/framework/wcf/defining-and-specifying-faults.md)
