---
title: <serviceDebug>
ms.date: 03/30/2017
ms.assetid: 6d7ea986-f232-49fe-842c-f934d9966889
ms.openlocfilehash: 4eb79cc91ef489501c4c8bb6311f240d855ed053
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399633"
---
# \<serviceDebug>
Gibt Debugging-und Hilfe Informationsfunktionen für einen Windows Communication Foundation (WCF)-Dienst an.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDebug>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<serviceDebug httpHelpPageBinding="String"
              httpHelpPageBindingConfiguration="String"
              httpHelpPageEnabled="Boolean"
              httpHelpPageUrl="Uri"
              httpsHelpPageBinding="String"
              httpsHelpPageBindingConfiguration="String"
              httpsHelpPageEnabled="Boolean"
              httpsHelpPageUrl="Uri"
              includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|httpHelpPageBinding|Ein Zeichenfolgenwert, der den Typ der zu verwendenden Bindung beim Zugriff auf die Diensthilfeseite über HTTP festlegt.<br /><br /> Nur Bindungen mit inneren Bindungselementen, die <xref:System.ServiceModel.Channels.IReplyChannel?displayProperty=nameWithType> unterstützen, werden unterstützt. Darüber hinaus muss die <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>-Eigenschaft der Bindung <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType> lauten.|  
|httpHelpPageBindingConfiguration|Eine Zeichenfolge mit dem Namen der Bindung, die im `httpHelpPageBinding`-Attribut angegeben ist, das auf die zusätzlichen Konfigurationsinformationen dieser Bindung verweist. Der gleiche Name muss im Abschnitt `<bindings>` definiert werden.|  
|httpHelpPageEnabled|Ein boolescher Wert, der steuert, ob WCF eine HTML-Hilfeseite an der vom-Attribut angegebenen Adresse veröffentlicht `httpHelpPageUrl` . Der Standardwert lautet `true`.<br /><br /> Sie können diese Eigenschaft auf `false` festlegen, um die Veröffentlichung einer in HTML-Browsern angezeigbaren HTML-Hilfeseite zu deaktivieren.<br /><br /> Um sicherzustellen, dass die HTML-Hilfeseite an dem Speicherort veröffentlicht wird, der vom `httpHelpPageUrl`-Attribut gesteuert wird, müssen Sie dieses Attribut auf `true` festlegen. Außerdem muss eine der folgenden Bedingungen erfüllt werden:<br /><br /> -Das- `httpHelpPageUrl` Attribut ist eine absolute Adresse, die das HTTP-Protokoll Schema unterstützt.<br />-Es gibt eine Basisadresse für den Dienst, der das HTTP-Protokoll Schema unterstützt.<br /><br /> Obwohl eine Ausnahme ausgegeben wird, wenn eine absolute Adresse, die das HTTP-Protokollschema nicht unterstützt, dem `httpHelpPageUrl`-Attribut zugewiesen wird, werden bei allen anderen Szenarien, die den vorstehenden Kriterien nicht entsprechen, keine Ausnahmen und HTML-Hilfeseiten ausgegeben.|  
|httpHelpPageUrl|Ein URI, der die relative oder absolute HTTP-basierte URL der benutzerdefinierten HTML-Hilfedatei angibt, die dem Benutzer angezeigt wird, wenn der Endpunkt mithilfe eines HTML-Browsers angezeigt wird.<br /><br /> Sie können dieses Attribut verwenden, um die Verwendung einer benutzerdefinierten HTML-Hilfedatei zu ermöglichen, die von einer HTTP/Get-Anfrage zurückgegeben wird, beispielsweise von einem HTML-Browser. Der Speicherort der HTML-Hilfedatei wird wie folgt aufgelöst.<br /><br /> 1. wenn der Wert dieses Attributs eine relative Adresse ist, entspricht der Speicherort der HTML-Hilfedatei dem Wert der Dienst Basisadresse, die HTTP-Anforderungen unterstützt, plus dieses Eigenschafts Werts.<br />2. wenn der Wert dieses Attributs eine absolute Adresse ist und HTTP-Anforderungen unterstützt, entspricht der Speicherort der HTML-Hilfedatei dem Wert dieser Eigenschaft.<br />3. wenn der Wert dieses Attributs absolut ist, aber keine HTTP-Anforderungen unterstützt, wird eine Ausnahme ausgelöst.<br /><br /> Dieses Attribut ist nur gültig, wenn das- `httpHelpPageEnabled` Attribut ist `true` .|  
|httpsHelpPageBinding|Ein Zeichenfolgenwert, der den Typ der zu verwendenden Bindung beim Zugriff auf die Diensthilfeseite über HTTPS festlegt.<br /><br /> Nur Bindungen mit inneren Bindungselementen, die <xref:System.ServiceModel.Channels.IReplyChannel> unterstützen, werden unterstützt. Darüber hinaus muss die <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>-Eigenschaft der Bindung <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType> lauten.|  
|httpsHelpPageBindingConfiguration|Eine Zeichenfolge mit dem Namen der Bindung, die im `httpsHelpPageBinding`-Attribut angegeben ist, das auf die zusätzlichen Konfigurationsinformationen dieser Bindung verweist. Der gleiche Name muss im Abschnitt `<bindings>` definiert werden.|  
|httpsHelpPageEnabled|Ein boolescher Wert, der steuert, ob WCF eine HTML-Hilfeseite an der vom-Attribut angegebenen Adresse veröffentlicht `httpsHelpPageUrl` . Der Standardwert lautet `true`.<br /><br /> Sie können diese Eigenschaft auf `false` festlegen, um die Veröffentlichung einer in HTML-Browsern angezeigbaren HTML-Hilfeseite zu deaktivieren.<br /><br /> Um sicherzustellen, dass die HTML-Hilfeseite an dem Speicherort veröffentlicht wird, der vom `httpsHelpPageUrl`-Attribut gesteuert wird, müssen Sie dieses Attribut auf `true` festlegen. Außerdem muss eine der folgenden Bedingungen erfüllt werden:<br /><br /> -Das- `httpsHelpPageUrl` Attribut ist eine absolute Adresse, die das HTTPS-Protokoll Schema unterstützt.<br />-Es gibt eine Basisadresse für den Dienst, der das HTTPS-Protokoll Schema unterstützt.<br /><br /> Obwohl eine Ausnahme ausgegeben wird, wenn eine absolute Adresse, die das HTTPS-Protokollschema nicht unterstützt, dem `httpsHelpPageUrl`-Attribut zugewiesen wird, werden bei allen anderen Szenarien, die den vorstehenden Kriterien nicht entsprechen, keine Ausnahmen und HTML-Hilfeseiten ausgegeben.|  
|httpsHelpPageUrl|Ein URI, der die relative oder absolute HTTPS-basierte URL der benutzerdefinierten HTML-Hilfedatei angibt, die dem Benutzer angezeigt wird, wenn der Endpunkt mithilfe eines HTML-Browsers angezeigt wird.<br /><br /> Sie können dieses Attribut verwenden, um die Verwendung einer benutzerdefinierten HTML-Hilfedatei zu ermöglichen, die von einer HTTPS/Get-Anfrage zurückgegeben wird, beispielsweise von einem HTML-Browser. Der Speicherort der HTML-Hilfedatei wird wie folgt aufgelöst:<br /><br /> Wenn der Wert dieser Eigenschaft eine relative Adresse ist, entspricht der Speicherort der HTML-Hilfedatei dem Wert der Dienst Basisadresse, die HTTPS-Anforderungen unterstützt, plus dieses Eigenschafts Werts.<br />Wenn der Wert dieser Eigenschaft eine absolute Adresse ist und HTTPS-Anforderungen unterstützt, entspricht der Speicherort der HTML-Hilfedatei dem Wert dieser Eigenschaft.<br />Wenn der Wert dieser Eigenschaft absolut ist, aber keine HTTPS-Anforderungen unterstützt, wird eine Ausnahme ausgelöst.<br /><br /> Dieses Attribut ist nur gültig, wenn das- `httpHelpPageEnabled` Attribut ist `true` .|  
|includeExceptionDetailInFaults|Ein Wert, der angibt, ob verwaltete Ausnahmeinformationen in den Details der SOAP-Fehler zu Debuggingzwecken an den Client zurückgegeben werden. Der Standardwert lautet `false`.<br /><br /> Wenn Sie dieses Attribut auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen zurück an den Client zu Debuggingzwecken aktivieren und die Veröffentlichung von HTML-Informationsdateien für Benutzer bereitstellen, die den Dienst in Webbrowsern durchsuchen. **Vorsicht:**  Das Zurückgeben von Informationen zu verwalteten Ausnahmen an Clients kann ein Sicherheitsrisiko darstellen. Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="remarks"></a>Bemerkungen  
 `includeExceptionDetailInFaults`Wenn Sie auf festlegen, `true` kann der Dienst jede Ausnahme zurückgeben, die vom Anwendungscode ausgelöst wird, auch wenn die Ausnahme nicht mithilfe von deklariert wurde <xref:System.ServiceModel.FaultContractAttribute> . Diese Einstellung ist in Debuggingfällen hilfreich, in denen der Server eine unerwartete Ausnahme ausgibt. Durch Verwenden dieses Attributs wird ein serialisiertes Format der unbekannten Ausnahme zurückgegeben, und Sie können mehr Details zur Ausnahme überprüfen.  
  
> [!CAUTION]
> Verwaltete Ausnahmeinformationen an Clients zurückzugeben kann ein Sicherheitsrisiko darstellen, da Ausnahmedetails Informationen zur internen Dienstimplementierung verfügbar machen, die von nicht autorisierten Clients verwendet werden könnten. Wegen der damit verbundenen Sicherheitsprobleme wird dringend empfohlen, dass Sie diesen Vorgang nur in gesteuerten Debugszenarien ausführen. Beim Bereitstellen der Anwendung sollten Sie `includeExceptionDetailInFaults` auf `false` festlegen.  
  
 Ausführliche Informationen zu den Sicherheitsproblemen im Zusammenhang mit der verwalteten Ausnahme finden Sie unter [angeben und behandeln von Fehlern in Verträgen und Diensten](../../../wcf/specifying-and-handling-faults-in-contracts-and-services.md). Ein Codebeispiel finden Sie unter [Debugverhalten von Diensten](../../../wcf/samples/service-debug-behavior.md).  
  
 Sie können auch `httpsHelpPageEnabled` und `httpsHelpPageUrl` festlegen, um die Hilfeseite zu aktivieren oder zu deaktivieren. Jeder Dienst kann optional eine Hilfeseite verfügbar machen, die Informationen zum Dienst enthält, einschließlich des Endpunkts, um WSDL für den Dienst abzurufen. Dies kann durch Festlegen von `httpHelpPageEnabled` auf `true` aktiviert werden. Dadurch kann die Hilfeseite an eine GET-Anforderung der Basisadresse des Diensts zurückgegeben werden. Durch Festlegen des `httpHelpPageUrl`-Attributs können Sie diese Adresse ändern. Sie können dies außerdem sichern, indem Sie HTTPS statt HTTP verwenden.  
  
 Mithilfe des optionalen `httpHelpPageBinding`-Attributs und `httpHelpPageBinding`-Attributs können Sie die für den Zugriff auf die Diensthilfeseite verwendeten Bindungen konfigurieren. Wenn sie nicht festgelegt sind, werden die Standardbindungen (`HttpTransportBindingElement` für HTTP und `HttpsTransportBindingElement` für HTTPS) entsprechend für den Zugriff auf die Diensthilfeseite verwendet. Beachten Sie, dass Sie diese Attribute nicht mit den integrierten WCF-Bindungen verwenden können. Nur Bindungen mit inneren Bindungs Elementen, die Xref: System. Service Model. Channels. IReplyChannel-> unterstützen, werden unterstützt. Darüber hinaus muss die <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>-Eigenschaft der Bindung <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType> lauten.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.ServiceDebugElement>
- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
- [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../wcf/specifying-and-handling-faults-in-contracts-and-services.md)
- [Behandeln von Ausnahmen und Fehlern](../../../wcf/extending/handling-exceptions-and-faults.md)
- [Debugverhalten von Diensten](../../../wcf/samples/service-debug-behavior.md)
