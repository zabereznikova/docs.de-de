---
title: Aktivieren des Transaktionsflusses
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: transactions [WCF], enabling flow
ms.assetid: a03f5041-5049-43f4-897c-e0292d4718f7
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b5d0b90ed28928e734089265cb8c58839b6d0cd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="enabling-transaction-flow"></a>Aktivieren des Transaktionsflusses
Der Transaktionsfluss kann in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] mit sehr flexiblen Optionen gesteuert werden. Die Transaktionsflusseinstellungen eines Dienstes können durch eine Kombination aus Attributen und Konfigurationen ausgedrückt werden.  
  
## <a name="transaction-flow-settings"></a>Transaktionsflusseinstellungen  
 Transaktionsflusseinstellungen werden als Ergebnis einer Schnittmenge aus den folgenden drei Werten für einen Dienstendpunkt generiert:  
  
-   Dem <xref:System.ServiceModel.TransactionFlowAttribute>-Attribut, das für jede Methode im Dienstvertrag angegeben wird.  
  
-   Der `TransactionFlow`-Bindungseigenschaft in der speziellen Bindung.  
  
-   Der `TransactionFlowProtocol`-Bindungseigenschaft in der speziellen Bindung. Mit der `TransactionFlowProtocol`-Bindungseigenschaft können Sie eines von zwei unterschiedlichen Transaktionsprotokollen für einen Transaktionsfluss auswählen. Diese Protokolle werden jeweils in den folgenden Abschnitten kurz erläutert.  
  
### <a name="ws-atomictransaction-protocol"></a>WS-AtomicTransaction-Protokoll  
 Das WS-AtomicTransaction-Protokoll (WS-AT) eignet sich für Szenarien, in denen die Interoperabilität mit Protokollstapeln eines Drittanbieters erforderlich ist.  
  
### <a name="oletransactions-protocol"></a>OleTransactions-Protokoll  
 Das OleTransactions-Protokoll eignet sich für Szenarien, in denen die Interoperabilität mit Protokollstapeln eines Drittanbieters nicht erforderlich ist und der Bereitsteller des Dienstes im Voraus weiß, dass der WS-AT-Protokolldienst lokal deaktiviert ist oder die vorhandene Netzwerktopologie die Verwendung von WS-AT nicht unterstützt.  
  
 In der folgenden Tabelle werden die unterschiedlichen Transaktionsflüsse aufgeführt, die mit den verschiedenen Kombinationen generiert verwendet werden können.  
  
|TransactionFlow-<br /><br /> Bindung|TransactionFlow-Bindungseigenschaft|TransactionFlowProtocol-Bindungsprotokoll|Typ des Transaktionsflusses|  
|---------------------------------|--------------------------------------|----------------------------------------------|------------------------------|  
|Erforderlich|true|WS-AT|Der Transaktionsfluss muss im interoperablen WS-AT-Format erfolgen.|  
|Erforderlich|true|OleTransactions|Der Transaktionsfluss muss im OleTransactions-Format von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erfolgen.|  
|Erforderlich|false|Nicht zutreffend|Nicht zutreffend, da es sich um eine ungültige Konfiguration handelt.|  
|Allowed|true|WS-AT|Der Transaktionsfluss kann im interoperablen WS-AT-Format erfolgen.|  
|Allowed|true|OleTransactions|Der Transaktionsfluss kann im OleTransactions-Format von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erfolgen.|  
|Allowed|false|Beliebiger Wert|Es erfolgt kein Transaktionsfluss.|  
|NotAllowed|Beliebiger Wert|Beliebiger Wert|Es erfolgt kein Transaktionsfluss.|  
  
 In der folgenden Tabelle wird das Ergebnis der Nachrichtenverarbeitung zusammengefasst.  
  
|Eingehende Nachricht|TransactionFlow-Einstellung|Transaktionsheader|Ergebnis der Nachrichtenverarbeitung|  
|----------------------|-----------------------------|------------------------|-------------------------------|  
|Die Transaktion stimmt mit dem erwarteten Protokollformat überein.|Allowed oder Mandatory|`MustUnderstand` ist gleich `true`.|Prozess|  
|Die Transaktion stimmt nicht mit dem erwarteten Protokollformat überein.|Erforderlich|`MustUnderstand` ist gleich `false`.|Abgelehnt, da eine Transaktion erforderlich ist.|  
|Die Transaktion stimmt nicht mit dem erwarteten Protokollformat überein.|Allowed|`MustUnderstand` ist gleich `false`.|Abgelehnt, da der Header nicht interpretiert werden kann.|  
|Transaktion mit einem beliebigen Protokollformat|NotAllowed|`MustUnderstand` ist gleich `false`.|Abgelehnt, da der Header nicht interpretiert werden kann.|  
|Keine Transaktion|Erforderlich|Nicht zutreffend|Abgelehnt, da eine Transaktion erforderlich ist.|  
|Keine Transaktion|Allowed|Nicht zutreffend|Prozess|  
|Keine Transaktion|NotAllowed|Nicht zutreffend|Prozess|  
  
 Jede Methode eines Vertrags kann zwar verschiedene Transaktionsflussanforderungen aufweisen, die Einstellung des Transaktionsflussprotokolls wird jedoch auf der Bindungsebene festgelegt. Das bedeutet, dass alle Methoden, die denselben Endpunkt gemeinsam nutzen (und somit dieselbe Bindung), auch dieselbe Richtlinie verwenden, die einen Transaktionsfluss zulässt oder verlangt, sowie gegebenenfalls dasselbe Transaktionsprotokoll.  
  
## <a name="enabling-transaction-flow-at-the-method-level"></a>Aktivieren des Transaktionsflusses auf der Methodenebene  
 Transaktionsflussanforderungen sind nicht immer für alle Methoden in einem Dienstvertrag identisch. Deshalb stellt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auch einen auf Attributen basierenden Mechanismus bereit, mit dem die Transaktionsflusseinstellungen für jede Methode ausgedrückt werden können. Dazu wird mit <xref:System.ServiceModel.TransactionFlowAttribute> die Ebene angegeben, auf der ein Dienstvorgang einen Transaktionsheader akzeptiert. Kennzeichnen Sie die Methoden des Dienstvertrags mit diesem Attribut, wenn Sie den Transaktionsfluss aktivieren möchten. Dieses Attribut verwendet einen der Werte der <xref:System.ServiceModel.TransactionFlowOption>-Enumeration, wobei hier der Standardwert <xref:System.ServiceModel.TransactionFlowOption.NotAllowed> lautet. Wenn ein anderer Wert als <xref:System.ServiceModel.TransactionFlowOption.NotAllowed> angegeben wird, darf die Methode nicht unidirektional sein. Ein Entwickler kann mit diesem Attribut Transaktionsflussanforderungen auf Methodenebene oder Einschränkungen zur Entwurfszeit angeben.  
  
## <a name="enabling-transaction-flow-at-the-endpoint-level"></a>Aktivieren des Transaktionsflusses auf der Endpunktebene  
 Abgesehen von der Transaktionsflusseinstellung auf Methodenebene, die das <xref:System.ServiceModel.TransactionFlowAttribute>-Attribute ermöglicht, stellt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eine Einstellung für den gesamten Endpunkt bereit, mit der der Transaktionsfluss auf einer höheren Ebene gesteuert werden kann.  
  
 Sie verwenden dazu <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>. Damit können Sie den eingehenden Transaktionsfluss in der Bindungseinstellung eines Endpunkts aktivieren oder deaktivieren und das gewünschte Transaktionsprotokollformat für eingehende Transaktionen angeben.  
  
 Wenn der Transaktionsfluss der Bindung deaktiviert ist, jedoch einer der Vorgänge eines Dienstvertrags eine eingehende Transaktion erfordert, wird beim Starten des Dienstes eine Validierungsausnahme ausgelöst.  
  
 Die meisten der von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Bindungen enthalten die Attribute `transactionFlow` und `transactionProtocol`, sodass Sie die spezielle Bindung für die Annahme eingehender Transaktionen konfigurieren können. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]die Konfigurationselemente finden Sie unter [ \<Bindung >](../../../../docs/framework/misc/binding.md).  
  
 Ein Administrator oder Bereitsteller kann den Transaktionsfluss auf Endpunktebene verwenden, um mithilfe der Konfigurationsdatei Transaktionsflussanforderungen oder Einschränkungen zur Bereitstellungszeit zu konfigurieren.  
  
## <a name="security"></a>Sicherheit  
 Sichern Sie den Nachrichtenaustausch während des Transaktionsflusses zwischen Anwendungen, um die Sicherheit und Integrität des Systems zu gewährleisten. Übertragen oder vermitteln Sie keine Transaktionsdetails an Anwendungen, die nicht zur Teilnahme an derselben Transaktion berechtigt sind.  
  
 Wenn Sie unter Verwendung eines Metadatenaustausches [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients für unbekannte oder nicht vertrauenswürdige Webdienste generieren, sollten Vorgänge zu diesen Webdiensten möglichst die aktuelle Transaktion unterdrücken. Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.  
  
```  
//client code which has an ambient transaction  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Suppress))  
{  
    // No transaction will flow to this operation  
    untrustedProxy.Operation1(...);  
    scope.Complete();  
}  
//remainder of client code  
```  
  
 Konfigurieren Sie Dienste außerdem so, dass sie eingehende Transaktionen nur von authentifizierten und autorisierten Clients akzeptieren. Eingehende Transaktionen sollten nur von absolut vertrauenswürdigen Clients angenommen werden.  
  
## <a name="policy-assertions"></a>Richtlinienassertionen  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet Richtlinienassertionen, um den Transaktionsfluss zu steuern. Richtlinienassertionen befinden sich im Richtliniendokument eines Dienstes, das durch Aggregation von Verträgen, Konfigurationen und Attributen generiert wird. Der Client kann das Richtliniendokument des Dienstes mit einem HTTP GET- oder WS-MetadataExchange-Anforderungs-/Anwortvorgang abrufen. Anschließend kann der Client das Richtliniendokument verarbeiten und ermitteln, welche Vorgänge zu einem Dienstvertrag einen Transaktionsfluss unterstützen oder erfordern.  
  
 Transaktionsfluss-Richtlinienassertionen beeinflussen den Transaktionsfluss durch Angabe der SOAP-Header, die ein Client an einen Dienst senden muss, um eine Transaktion darzustellen. Alle Transaktionsheader müssen mit`MustUnderstand` gleich `true` gekennzeichnet sein. Jede Nachricht mit einem anders gekennzeichneten Header wird mit einem SOAP-Fehler abgelehnt.  
  
 Für einen einzelnen Vorgang kann es nur eine transaktionsbezogene Richtlinienassertion geben. Richtliniendokumente mit mehreren Transaktionsassertionen für einen Vorgang sind ungültig und werden von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] abgelehnt. Darüber hinaus kann nur ein einziges Transaktionsprotokoll in den einzelnen Anschlusstypen vorhanden sein. Richtliniendokumente mit Verweisen auf mehr als ein Transaktionsprotokoll in einer einzelnen Anschlusstypen Vorgänge werden als ungültig betrachtet, und werden vom zurückgewiesen der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Richtliniendokumente mit Transaktionsassertionen zu Ausgabenachrichten oder unidirektionalen Eingabenachrichten sind ebenfalls ungültig.
