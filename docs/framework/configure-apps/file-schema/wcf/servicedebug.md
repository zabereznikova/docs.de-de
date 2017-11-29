---
title: '&lt;serviceDebug&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d7ea986-f232-49fe-842c-f934d9966889
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fbc201719f467ad35d1c8f524bfd539d293359be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicedebuggt"></a>&lt;serviceDebug&gt;
Gibt Debugging- und Hilfeinformationsfeatures für einen [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Dienst an.  
  
 \<System. ServiceModel >  
\<Verhalten >  
\<ServiceBehaviors >  
\<Verhalten >  
\<ServiceDebug >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<serviceDebug     httpHelpPageBinding="String"    httpHelpPageBindingConfiguration="String"  
    httpHelpPageEnabled="Boolean"  
    httpHelpPageUrl="Uri"  
    httpsHelpPageBinding="String"    httpsHelpPageBindingConfiguration="String"  
    httpsHelpPageEnabled="Boolean"  
    httpsHelpPageUrl="Uri"  
    includeExceptionDetailInFaults="Boolean" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|httpHelpPageBinding|Ein Zeichenfolgenwert, der den Typ der zu verwendenden Bindung beim Zugriff auf die Diensthilfeseite über HTTP festlegt.<br /><br /> Nur Bindungen mit inneren Bindungselementen, die <xref:System.ServiceModel.Channels.IReplyChannel?displayProperty=nameWithType> unterstützen, werden unterstützt. Darüber hinaus muss die <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>-Eigenschaft der Bindung <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType> lauten.|  
|httpHelpPageBindingConfiguration|Eine Zeichenfolge mit dem Namen der Bindung, die im `httpHelpPageBinding`-Attribut angegeben ist, das auf die zusätzlichen Konfigurationsinformationen dieser Bindung verweist. Der gleiche Name muss im Abschnitt `<bindings>` definiert werden.|  
|httpHelpPageEnabled|Ein boolescher Wert, der steuert, ob [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] eine HTML-Hilfeseite an der vom `httpHelpPageUrl`-Attribut angegebenen Adresse veröffentlicht. Die Standardeinstellung ist `true`.<br /><br /> Sie können diese Eigenschaft auf `false` festlegen, um die Veröffentlichung einer in HTML-Browsern angezeigbaren HTML-Hilfeseite zu deaktivieren.<br /><br /> Um sicherzustellen, dass die HTML-Hilfeseite an dem Speicherort veröffentlicht wird, der vom `httpHelpPageUrl`-Attribut gesteuert wird, müssen Sie dieses Attribut auf `true` festlegen. Außerdem muss eine der folgenden Bedingungen erfüllt werden:<br /><br /> – Der `httpHelpPageUrl` Attribut ist eine absolute Adresse, die das HTTP-Protokollschema unterstützt.<br />– Es gibt eine Basisadresse für den Dienst, der das HTTP-Protokollschema unterstützt.<br /><br /> Obwohl eine Ausnahme ausgegeben wird, wenn eine absolute Adresse, die das HTTP-Protokollschema nicht unterstützt, dem `httpHelpPageUrl`-Attribut zugewiesen wird, werden bei allen anderen Szenarien, die den vorstehenden Kriterien nicht entsprechen, keine Ausnahmen und HTML-Hilfeseiten ausgegeben.|  
|httpHelpPageUrl|Ein URI, der die relative oder absolute HTTP-basierte URL der benutzerdefinierten HTML-Hilfedatei angibt, die dem Benutzer angezeigt wird, wenn der Endpunkt mithilfe eines HTML-Browsers angezeigt wird.<br /><br /> Sie können dieses Attribut verwenden, um die Verwendung einer benutzerdefinierten HTML-Hilfedatei zu ermöglichen, die von einer HTTP/Get-Anfrage zurückgegeben wird, beispielsweise von einem HTML-Browser. Der Speicherort der HTML-Hilfedatei wird wie folgt aufgelöst.<br /><br /> 1.  Wenn der Wert dieses Attributs eine relative Adresse ist, entspricht der Speicherort der HTML-Hilfedatei dem Wert der Dienstbasisadresse, die HTTP-Anforderungen unterstützt, plus dieses Eigenschaftswerts.<br />2.  Wenn der Wert dieses Attributs eine absolute Adresse ist und HTTP-Anforderungen unterstützt, entspricht der Speicherort der HTML-Hilfedatei dem Wert dieser Eigenschaft.<br />3.  Wenn der Wert dieses Attributs eine absolute Adresse ist, aber keine HTTP-Anforderungen unterstützt, wird eine Ausnahme ausgegeben.<br /><br /> Dieses Attribut ist nur gültig, wenn die `httpHelpPageEnabled` -Attribut ist `true`.|  
|httpsHelpPageBinding|Ein Zeichenfolgenwert, der den Typ der zu verwendenden Bindung beim Zugriff auf die Diensthilfeseite über HTTPS festlegt.<br /><br /> Nur Bindungen mit inneren Bindungselementen, die <xref:System.ServiceModel.Channels.IReplyChannel> unterstützen, werden unterstützt. Darüber hinaus muss die <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>-Eigenschaft der Bindung <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType> lauten.|  
|httpsHelpPageBindingConfiguration|Eine Zeichenfolge mit dem Namen der Bindung, die im `httpsHelpPageBinding`-Attribut angegeben ist, das auf die zusätzlichen Konfigurationsinformationen dieser Bindung verweist. Der gleiche Name muss im Abschnitt `<bindings>` definiert werden.|  
|httpsHelpPageEnabled|Ein boolescher Wert, der steuert, ob [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] eine HTML-Hilfeseite an der vom `httpsHelpPageUrl`-Attribut angegebenen Adresse veröffentlicht. Die Standardeinstellung ist `true`.<br /><br /> Sie können diese Eigenschaft auf `false` festlegen, um die Veröffentlichung einer in HTML-Browsern angezeigbaren HTML-Hilfeseite zu deaktivieren.<br /><br /> Um sicherzustellen, dass die HTML-Hilfeseite an dem Speicherort veröffentlicht wird, der vom `httpsHelpPageUrl`-Attribut gesteuert wird, müssen Sie dieses Attribut auf `true` festlegen. Außerdem muss eine der folgenden Bedingungen erfüllt werden:<br /><br /> – Der `httpsHelpPageUrl` Attribut ist eine absolute Adresse, die das HTTPS-Protokollschema unterstützt.<br />– Es gibt eine Basisadresse für den Dienst, der das HTTPS-Protokollschema unterstützt.<br /><br /> Obwohl eine Ausnahme ausgegeben wird, wenn eine absolute Adresse, die das HTTPS-Protokollschema nicht unterstützt, dem `httpsHelpPageUrl`-Attribut zugewiesen wird, werden bei allen anderen Szenarien, die den vorstehenden Kriterien nicht entsprechen, keine Ausnahmen und HTML-Hilfeseiten ausgegeben.|  
|httpsHelpPageUrl|Ein URI, der die relative oder absolute HTTPS-basierte URL der benutzerdefinierten HTML-Hilfedatei angibt, die dem Benutzer angezeigt wird, wenn der Endpunkt mithilfe eines HTML-Browsers angezeigt wird.<br /><br /> Sie können dieses Attribut verwenden, um die Verwendung einer benutzerdefinierten HTML-Hilfedatei zu ermöglichen, die von einer HTTPS/Get-Anfrage zurückgegeben wird, beispielsweise von einem HTML-Browser. Der Speicherort der HTML-Hilfedatei wird wie folgt aufgelöst:<br /><br /> – Wenn der Wert dieser Eigenschaft eine relative Adresse ist, ist der Speicherort der HTML-Hilfedatei, den Wert der dienstbasisadresse, die HTTPS-Anforderungen unterstützt, plus dieses Eigenschaftswerts.<br />– Wenn der Wert dieser Eigenschaft eine absolute Adresse und HTTPS-Anforderungen unterstützt, ist der Speicherort der HTML-Hilfedatei dem Wert dieser Eigenschaft.<br />– Wenn der Wert dieser Eigenschaft absolut ist, aber keine HTTPS-Anforderungen unterstützt, wird eine Ausnahme ausgelöst.<br /><br /> Dieses Attribut ist nur gültig, wenn die `httpHelpPageEnabled` -Attribut ist `true`.|  
|includeExceptionDetailInFaults|Ein Wert, der angibt, ob verwaltete Ausnahmeinformationen in den Details der SOAP-Fehler zu Debuggingzwecken an den Client zurückgegeben werden. Die Standardeinstellung ist `false`.<br /><br /> Wenn Sie dieses Attribut auf `true` festlegen, können Sie die Übergabe von verwalteten Ausnahmeinformationen zurück an den Client zu Debuggingzwecken aktivieren und die Veröffentlichung von HTML-Informationsdateien für Benutzer bereitstellen, die den Dienst in Webbrowsern durchsuchen. **Vorsicht:** zurückgeben, verwaltete Ausnahmeinformationen an Clients kann ein Sicherheitsrisiko sein. Das liegt darin begründet, dass Ausnahmedetails Informationen zur internen Dienstimplementierung offen legen, die von nicht autorisierten Clients verwendet werden können.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Verhalten >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="remarks"></a>Hinweise  
 Festlegen von `includeExceptionDetailInFaults` auf `true` ermöglicht es dem Dienst Ausnahmen zurückgeben, die von der Anwendung ausgelöst wird, selbst wenn die Ausnahme nicht deklariert ist, mit der <xref:System.ServiceModel.FaultContractAttribute>. Diese Einstellung ist in Debuggingfällen hilfreich, in denen der Server eine unerwartete Ausnahme ausgibt. Durch Verwenden dieses Attributs wird ein serialisiertes Format der unbekannten Ausnahme zurückgegeben, und Sie können mehr Details zur Ausnahme überprüfen.  
  
> [!CAUTION]
>  Verwaltete Ausnahmeinformationen an Clients zurückzugeben kann ein Sicherheitsrisiko darstellen, da Ausnahmedetails Informationen zur internen Dienstimplementierung verfügbar machen, die von nicht autorisierten Clients verwendet werden könnten. Wegen der damit verbundenen Sicherheitsprobleme wird dringend empfohlen, dass Sie diesen Vorgang nur in gesteuerten Debugszenarien ausführen. Beim Bereitstellen der Anwendung sollten Sie `includeExceptionDetailInFaults` auf `false` festlegen.  
  
 Informationen zu Sicherheitsproblemen, die im Zusammenhang mit verwalteten Ausnahmen finden Sie unter [angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md). Ein Codebeispiel finden Sie unter [Dienstverhalten Debuggen](../../../../../docs/framework/wcf/samples/service-debug-behavior.md).  
  
 Sie können auch `httpsHelpPageEnabled` und `httpsHelpPageUrl` festlegen, um die Hilfeseite zu aktivieren oder zu deaktivieren. Jeder Dienst kann optional eine Hilfeseite verfügbar machen, die Informationen zum Dienst enthält, einschließlich des Endpunkts, um WSDL für den Dienst abzurufen. Dies kann durch Festlegen von `httpHelpPageEnabled` auf `true` aktiviert werden. Dadurch kann die Hilfeseite an eine GET-Anforderung der Basisadresse des Diensts zurückgegeben werden. Durch Festlegen des `httpHelpPageUrl`-Attributs können Sie diese Adresse ändern. Sie können dies außerdem sichern, indem Sie HTTPS statt HTTP verwenden.  
  
 Mithilfe des optionalen `httpHelpPageBinding`-Attributs und `httpHelpPageBinding`-Attributs können Sie die für den Zugriff auf die Diensthilfeseite verwendeten Bindungen konfigurieren. Wenn sie nicht festgelegt sind, werden die Standardbindungen (`HttpTransportBindingElement` für HTTP und `HttpsTransportBindingElement` für HTTPS) entsprechend für den Zugriff auf die Diensthilfeseite verwendet. Beachten Sie, dass Sie diese Attribute nicht mit den integrierten WCF-Bindungen verwenden können. Nur Bindungen mit inneren Bindungselementen, die xref:System.ServiceModel.Channels.IReplyChannel unterstützen > wird unterstützt. Darüber hinaus muss die <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>-Eigenschaft der Bindung <xref:System.ServiceModel.Channels.MessageVersion.None?displayProperty=nameWithType> lauten.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ServiceDebugElement>  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>  
 [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)  
 [Behandeln von Ausnahmen und Fehlern](../../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)  
 [Debugverhalten von Diensten](../../../../../docs/framework/wcf/samples/service-debug-behavior.md)
