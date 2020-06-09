---
title: Aktivieren des Transaktionsflusses
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], enabling flow
ms.assetid: a03f5041-5049-43f4-897c-e0292d4718f7
ms.openlocfilehash: 5cea72e503087ac2a8f3b6ff2a07c2919ee00630
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597422"
---
# <a name="enabling-transaction-flow"></a>Aktivieren des Transaktionsflusses
Windows Communication Foundation (WCF) bietet hochgradig flexible Optionen zum Steuern des Transaktions Flusses. Die Transaktionsflusseinstellungen eines Dienstes können durch eine Kombination aus Attributen und Konfigurationen ausgedrückt werden.  
  
## <a name="transaction-flow-settings"></a>Transaktionsflusseinstellungen  
 Transaktionsflusseinstellungen werden als Ergebnis einer Schnittmenge aus den folgenden drei Werten für einen Dienstendpunkt generiert:  
  
- Dem <xref:System.ServiceModel.TransactionFlowAttribute>-Attribut, das für jede Methode im Dienstvertrag angegeben wird.  
  
- Der `TransactionFlow`-Bindungseigenschaft in der speziellen Bindung.  
  
- Der `TransactionFlowProtocol`-Bindungseigenschaft in der speziellen Bindung. Mit der `TransactionFlowProtocol`-Bindungseigenschaft können Sie eines von zwei unterschiedlichen Transaktionsprotokollen für einen Transaktionsfluss auswählen. Diese Protokolle werden jeweils in den folgenden Abschnitten kurz erläutert.  
  
### <a name="ws-atomictransaction-protocol"></a>WS-AtomicTransaction-Protokoll  
 Das WS-AtomicTransaction-Protokoll (WS-AT) eignet sich für Szenarien, in denen die Interoperabilität mit Protokollstapeln eines Drittanbieters erforderlich ist.  
  
### <a name="oletransactions-protocol"></a>OleTransactions-Protokoll  
 Das OleTransactions-Protokoll eignet sich für Szenarien, in denen die Interoperabilität mit Protokollstapeln eines Drittanbieters nicht erforderlich ist und der Bereitsteller des Dienstes im Voraus weiß, dass der WS-AT-Protokolldienst lokal deaktiviert ist oder die vorhandene Netzwerktopologie die Verwendung von WS-AT nicht unterstützt.  
  
 In der folgenden Tabelle werden die unterschiedlichen Transaktionsflüsse aufgeführt, die mit den verschiedenen Kombinationen generiert verwendet werden können.  
  
|TransactionFlow<br /><br /> binding|TransactionFlow-Bindungseigenschaft|TransactionFlowProtocol-Bindungsprotokoll|Typ des Transaktionsflusses|  
|---------------------------------|--------------------------------------|----------------------------------------------|------------------------------|  
|Obligatorisch.|true|WS-AT|Der Transaktionsfluss muss im interoperablen WS-AT-Format erfolgen.|  
|Obligatorisch.|true|OleTransactions|Die Transaktion muss im WCF OleTransactions-Format übertragen werden.|  
|Obligatorisch.|false|Nicht verfügbar|Nicht zutreffend, da es sich um eine ungültige Konfiguration handelt.|  
|Zulässig|true|WS-AT|Der Transaktionsfluss kann im interoperablen WS-AT-Format erfolgen.|  
|Zulässig|true|OleTransactions|Die Transaktion kann im WCF OleTransactions-Format übertragen werden.|  
|Zulässig|false|Beliebiger Wert|Es erfolgt kein Transaktionsfluss.|  
|Nicht zulässig|Beliebiger Wert|Beliebiger Wert|Es erfolgt kein Transaktionsfluss.|  
  
 In der folgenden Tabelle wird das Ergebnis der Nachrichtenverarbeitung zusammengefasst.  
  
|Eingehende Nachricht|TransactionFlow-Einstellung|Transaktionsheader|Ergebnis der Nachrichtenverarbeitung|  
|----------------------|-----------------------------|------------------------|-------------------------------|  
|Die Transaktion stimmt mit dem erwarteten Protokollformat überein.|Allowed oder Mandatory|`MustUnderstand` ist gleich `true`.|Prozess|  
|Die Transaktion stimmt nicht mit dem erwarteten Protokollformat überein.|Obligatorisch.|`MustUnderstand` ist gleich `false`.|Abgelehnt, da eine Transaktion erforderlich ist.|  
|Die Transaktion stimmt nicht mit dem erwarteten Protokollformat überein.|Zulässig|`MustUnderstand` ist gleich `false`.|Abgelehnt, da der Header nicht interpretiert werden kann.|  
|Transaktion mit einem beliebigen Protokollformat|Nicht zulässig|`MustUnderstand` ist gleich `false`.|Abgelehnt, da der Header nicht interpretiert werden kann.|  
|Keine Transaktion|Obligatorisch.|–|Abgelehnt, da eine Transaktion erforderlich ist.|  
|Keine Transaktion|Zulässig|–|Prozess|  
|Keine Transaktion|Nicht zulässig|–|Prozess|  
  
 Jede Methode eines Vertrags kann zwar verschiedene Transaktionsflussanforderungen aufweisen, die Einstellung des Transaktionsflussprotokolls wird jedoch auf der Bindungsebene festgelegt. Das bedeutet, dass alle Methoden, die denselben Endpunkt gemeinsam nutzen (und somit dieselbe Bindung), auch dieselbe Richtlinie verwenden, die einen Transaktionsfluss zulässt oder verlangt, sowie gegebenenfalls dasselbe Transaktionsprotokoll.  
  
## <a name="enabling-transaction-flow-at-the-method-level"></a>Aktivieren des Transaktionsflusses auf der Methodenebene  
 Transaktionsflussanforderungen sind nicht immer für alle Methoden in einem Dienstvertrag identisch. Daher stellt WCF außerdem einen Attribut basierten Mechanismus bereit, mit dem die Transaktions Fluss Einstellungen der einzelnen Methoden ausgedrückt werden können. Dazu wird mit <xref:System.ServiceModel.TransactionFlowAttribute> die Ebene angegeben, auf der ein Dienstvorgang einen Transaktionsheader akzeptiert. Kennzeichnen Sie die Methoden des Dienstvertrags mit diesem Attribut, wenn Sie den Transaktionsfluss aktivieren möchten. Dieses Attribut verwendet einen der Werte der <xref:System.ServiceModel.TransactionFlowOption>-Enumeration, wobei hier der Standardwert <xref:System.ServiceModel.TransactionFlowOption.NotAllowed> lautet. Wenn ein anderer Wert als <xref:System.ServiceModel.TransactionFlowOption.NotAllowed> angegeben wird, darf die Methode nicht unidirektional sein. Ein Entwickler kann mit diesem Attribut Transaktionsflussanforderungen auf Methodenebene oder Einschränkungen zur Entwurfszeit angeben.  
  
## <a name="enabling-transaction-flow-at-the-endpoint-level"></a>Aktivieren des Transaktionsflusses auf der Endpunktebene  
 Zusätzlich zu den Transaktions Fluss Einstellungen auf Methoden Ebene, die das- <xref:System.ServiceModel.TransactionFlowAttribute> Attribut bereitstellt, bietet WCF eine Endpunkt weite Einstellung für den Transaktions Fluss, damit Administratoren den Transaktions Fluss auf einer höheren Ebene steuern können.  
  
 Sie verwenden dazu <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>. Damit können Sie den eingehenden Transaktionsfluss in der Bindungseinstellung eines Endpunkts aktivieren oder deaktivieren und das gewünschte Transaktionsprotokollformat für eingehende Transaktionen angeben.  
  
 Wenn der Transaktionsfluss der Bindung deaktiviert ist, jedoch einer der Vorgänge eines Dienstvertrags eine eingehende Transaktion erfordert, wird beim Starten des Dienstes eine Validierungsausnahme ausgelöst.  
  
 Die meisten der von WCF bereitgestellten Bindungen enthalten `transactionFlow` die `transactionProtocol` Attribute und, damit Sie die jeweilige Bindung so konfigurieren können, dass eingehende Transaktionen akzeptiert werden. Weitere Informationen zum Festlegen der Konfigurationselemente finden Sie unter [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) .  
  
 Ein Administrator oder Bereitsteller kann den Transaktionsfluss auf Endpunktebene verwenden, um mithilfe der Konfigurationsdatei Transaktionsflussanforderungen oder Einschränkungen zur Bereitstellungszeit zu konfigurieren.  
  
## <a name="security"></a>Sicherheit  
 Sichern Sie den Nachrichtenaustausch während des Transaktionsflusses zwischen Anwendungen, um die Sicherheit und Integrität des Systems zu gewährleisten. Übertragen oder vermitteln Sie keine Transaktionsdetails an Anwendungen, die nicht zur Teilnahme an derselben Transaktion berechtigt sind.  
  
 Beim Erstellen von WCF-Clients für unbekannte oder nicht vertrauenswürdige Webdienste durch die Verwendung des Metadatenaustauschs sollten Aufrufe von Vorgängen für diese Webdienste die aktuelle Transaktion nach Möglichkeit unterdrücken. Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.  
  
```csharp
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
 WCF verwendet Richtlinien Assertionen, um den Transaktions Fluss zu steuern. Richtlinienassertionen befinden sich im Richtliniendokument eines Dienstes, das durch Aggregation von Verträgen, Konfigurationen und Attributen generiert wird. Der Client kann das Richtliniendokument des Dienstes mit einem HTTP GET- oder WS-MetadataExchange-Anforderungs-/Anwortvorgang abrufen. Anschließend kann der Client das Richtliniendokument verarbeiten und ermitteln, welche Vorgänge zu einem Dienstvertrag einen Transaktionsfluss unterstützen oder erfordern.  
  
 Transaktionsfluss-Richtlinienassertionen beeinflussen den Transaktionsfluss durch Angabe der SOAP-Header, die ein Client an einen Dienst senden muss, um eine Transaktion darzustellen. Alle Transaktionsheader müssen mit`MustUnderstand` gleich `true` gekennzeichnet sein. Jede Nachricht mit einem anders gekennzeichneten Header wird mit einem SOAP-Fehler abgelehnt.  
  
 Für einen einzelnen Vorgang kann es nur eine transaktionsbezogene Richtlinienassertion geben. Richtlinien Dokumente mit mehr als einer Transaktionsbestätigung für einen Vorgang werden als ungültig eingestuft und von WCF abgelehnt. Darüber hinaus kann nur ein einziges Transaktionsprotokoll in den einzelnen Anschlusstypen vorhanden sein. Richtlinien Dokumente mit Vorgängen, die auf mehr als ein Transaktionsprotokoll innerhalb eines einzelnen Porttyps verweisen, werden als ungültig eingestuft und durch das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)abgelehnt. Richtliniendokumente mit Transaktionsassertionen zu Ausgabenachrichten oder unidirektionalen Eingabenachrichten sind ebenfalls ungültig.
