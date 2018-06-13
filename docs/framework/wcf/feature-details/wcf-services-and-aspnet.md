---
title: WCF-Dienste und ASP.NET
ms.date: 03/30/2017
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
ms.openlocfilehash: 6cfd4f8a5dc2a7835cba409a37b09166e49e8df3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33506162"
---
# <a name="wcf-services-and-aspnet"></a>WCF-Dienste und ASP.NET
Dieses Thema erläutert hosting Windows Communication Foundation (WCF) Services Seite-an-Seite mit ASP.NET und das Hosten dieser im ASP.NET-Kompatibilitätsmodus.  
  
## <a name="hosting-wcf-side-by-side-with-aspnet"></a>Paralleles Hosten in WCF und in ASP.NET  
 In IIS (Internetinformationsdienste) gehosteten WCF-Dienste können sich befinden. ASPX-Seiten und ASMX-Webdiensten in einem einzelnen, gemeinsamen Anwendungsdomäne. ASP.NET bietet allgemeine Infrastrukturdienste, wie etwa AppDomain-Verwaltung und der dynamischen Kompilierung für WCF und die ASP.NET-HTTP-Laufzeit. Die Standardkonfiguration für WCF wird Seite-an-Seite mit ASP.NET.  
  
 ![WCF-Dienste und ASP .NET:: Freigeben von Zuständen](../../../../docs/framework/wcf/feature-details/media/hostingwcfwithaspnet.gif "HostingWCFwithASPNET")  
  
 Die ASP.NET-HTTP-Laufzeit ASP.NET-Anforderungen behandelt, aber nicht Teil der Verarbeitung von Anforderungen, die für WCF-Dienste gerichtet, obwohl diese Dienste in der gleichen AppDomain gehostet werden, da ASP.NET Inhalt ist. Stattdessen des WCF-Dienstmodells fängt der WCF-Diensten adressierte Nachrichten ab und leitet sie durch die WCF-Transport-/Kanalstapel.  
  
 Die Ergebnisse des parallelen Modells sind folgende:  
  
-   ASP.NET und WCF-Dienste können AppDomain-Zustand gemeinsam verwenden. Da die beiden Frameworks in derselben AppDomain koexistieren können, kann WCF auch AppDomain-Zustand mit ASP.NET (einschließlich statischen Variablen, Ereignisse usw.) freigeben.  
  
-   WCF-Dienste Verhalten einheitlich, unabhängig von hostumgebung und Transport. Die ASP.NET-HTTP-Laufzeit ist absichtlich an IIS/ASP.NET-Hostumgebung und HTTP-Kommunikation gekoppelt. Im Gegensatz dazu dient WCF für konsistentes Verhalten in Hostumgebungen (WCF verhält sich konsistent, sowohl innerhalb und außerhalb von IIS) und für Transporte (ein Diensts in IIS 7.0 und höher gehosteter verhält sich konsistent für alle Endpunkte, die es bereitstellt, auch wenn Einige dieser Endpunkte verwenden andere Protokolle als HTTP).  
  
-   Innerhalb einer AppDomain gelten von der HTTP-Laufzeit implementierte Funktionen ASP.NET-Inhalt, aber nicht für WCF. Viele HTTP-spezifischen Funktionen der ASP.NET-Anwendungsplattform gelten nicht für WCF-Dienste, die in einer AppDomain, die ASP.NET-Inhalt enthält gehostet. Im Folgenden sind Beispiele für diese Funktionen aufgeführt:  
  
    -   HttpContext: <xref:System.Web.HttpContext.Current%2A> ist immer `null` Wenn der Zugriff innerhalb eines WCF-Diensts. Verwendung <!--zz <xref:System.ServiceModel.OperationContext.Current.RequestContext>--> `RequestContext` stattdessen.  
  
    -   Dateibasierte Autorisierung: den WCF-Sicherheitsmodell lässt sich nicht für die Zugriffssteuerungsliste (ACL) auf die SVC-Datei des Diensts angewendet werden, wenn Sie entscheiden, ob eine dienstanforderung autorisiert ist.  
  
    -   Konfigurationsbasierte URL-Autorisierung: Entsprechend der WCF-Sicherheitsmodell nicht auf reduzierbar in System.Web angegebene URL-basierten Autorisierungsregeln \<Authorization >-Konfigurationselement. Diese Einstellungen sind für WCF-Anforderungen ignoriert, wenn ein Dienst in einem URL-Namespace, die von ASP gesichert befindet. NET URL-Autorisierungsregeln.  
  
    -   HttpModule-Erweiterbarkeit: den WCF--Hostinfrastruktur fängt WCF anfordert, wenn die <xref:System.Web.HttpApplication.PostAuthenticateRequest> -Ereignis ausgelöst wird und die Verarbeitung nicht an der ASP.NET-HTTP-Pipeline zurück. Module, die zum Abfangen von Anforderungen in späteren Phasen der Pipeline codiert sind werden WCF-Anforderungen nicht abgefangen werden.  
  
    -   ASP.NET-Identitätswechsel: standardmäßig WCF angewiesen immer ausgeführt wird wie IIS die Identität, verarbeiten, auch wenn ASP.NET festgelegt ist, können Sie mithilfe des System.Web-Identitätswechsel aktivieren \<Identität = "true" / > Konfigurationsoption.  
  
 Diese Einschränkungen gelten nur für in IIS gehostete WCF-Dienste. Das Verhalten des ASP.NET-Inhalts wird durch das Vorhandensein von WCF nicht beeinflusst.  
  
 WCF-Anwendungen, die Funktionalität von der HTTP-Pipeline erfordern sollten mit den WCF-äquivalente, Host und transport unabhängig:  
  
-   <xref:System.ServiceModel.OperationContext> anstelle von <xref:System.Web.HttpContext>.  
  
-   <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> statt der Datei-/URL-Autorisierung von ASP.NET.  
  
-   <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> oder benutzerdefinierte überlagerte Kanäle statt der HTTP-Module.  
  
-   Identitätswechsel für jeden Vorgang mithilfe von WCF statt System.Web-Identitätswechsels.  
  
 Alternativ können Sie erwägen, Ihre Dienste im ASP.NET-Kompatibilitätsmodus von WCF ausgeführt.  
  
## <a name="hosting-wcf-services-in-aspnet-compatibility-mode"></a>Hosten von WCF-Diensten im ASP.NET-Kompatibilitätsmodus  
 Obwohl die WCF-Modell für konsistentes Verhalten in Hostumgebungen und für Transporte konzipiert ist, sind häufig Szenarien, in denen eine Anwendung dieses Maß an Flexibilität nicht erforderlich sind. ASP.NET-Kompatibilitätsmodus von WCF eignet sich für Szenarien, die die Fähigkeit, Host außerhalb von IIS oder die Kommunikation über andere Protokolle als HTTP erfordert jedoch die Verwendung aller Funktionen der ASP.NET-Webanwendungsplattform.  
  
 Im Gegensatz zu der Seite-an-Seite-Standardkonfiguration, in dem die WCF--Hostinfrastruktur fängt der WCF-Nachrichten ab und leitet sie aus der HTTP-Pipeline, teilnehmen WCF-Dienste im ASP.NET-Kompatibilitätsmodus ausgeführt voll am ASP.NET HTTP-Anforderungslebenszyklus. Im Kompatibilitätsmodus, WCF-Dienste verwenden die HTTP-Pipeline über eine <xref:System.Web.IHttpHandler> Implementierung, die ähnliche Weise, wie Anforderungen für ASPX-Seiten und ASMX-Webdienste behandelt werden. Folglich verhält sich WCF identisch mit ASMX in Bezug auf die folgenden ASP.NET-Funktionen:  
  
-   <xref:System.Web.HttpContext>: WCF-Dienste im ASP.NET-Kompatibilitätsmodus ausgeführt erreichen <xref:System.Web.HttpContext.Current%2A> und den zugehörigen Status.  
  
-   Dateibasierte Autorisierung: WCF-Dienste im ASP.NET-Kompatibilitätsmodus ausgeführt, die Datei System-Zugriffssteuerungslisten (ACLs) auf die SVC Datei anfügen sicher sein können.  
  
-   Konfigurierbare URL-Autorisierung: ASP. NET URL-Autorisierungsregeln sind für WCF-Anforderungen erzwungen, wenn der WCF-Dienst im ASP.NET-Kompatibilitätsmodus ausgeführt wird.  
  
-   <xref:System.Web.HttpModuleCollection> Erweiterbarkeit: weil WCF-Dienste im ASP.NET-Kompatibilitätsmodus ausgeführt voll am ASP.NET HTTP-Anforderungslebenszyklus teilnehmen, alle HTTP-Module, die in der HTTP-Pipeline konfiguriert wird WCF-Anforderungen vor und nach dem Dienstaufruf arbeiten.  
  
-   ASP.NET-Identitätswechsel: WCF-Dienste ausgeführt, mit der aktuellen Identität, die der ASP.NET-Thread angenommen hat, der IIS-Prozessidentität unterscheiden sein kann, wenn ASP.NET-Identitätswechsel für die Anwendung aktiviert wurde. Wenn ASP.NET-Identitätswechsel als auch WCF-Identitätswechsel für einen bestimmten Dienstvorgang aktiviert sind, die dienstimplementierung letztlich unter der Identität ausgeführt von WCF abgerufen.  
  
 ASP.NET-Kompatibilitätsmodus von WCF wird auf Anwendungsebene über die folgende Konfiguration (befindet sich in der Anwendungsdatei "Web.config") aktiviert:  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />  
</system.serviceModel>  
```  
  
 Dieser Wert liegt standardmäßig "`true`" nicht angegeben. Wenn dieser Wert auf "`false`" gibt an, dass alle WCF-Dienste, die in der Anwendung ausgeführt wird, nicht im ASP.NET-Kompatibilitätsmodus ausgeführt werden.  
  
 Da der ASP.NET-Kompatibilitätsmodus Semantik der anforderungsverarbeitung impliziert, die grundlegend von der WCF-Standard sind, haben einzelnen dienstimplementierungen die Möglichkeit zu steuern, ob die Ausführung innerhalb einer Anwendung für die ASP.NET Kompatibilitätsmodus wurde aktiviert. Dienste können das <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> verwenden, um anzugeben, ob sie den ASP.NET-Kompatibilitätsmodus unterstützen. Der Standardwert für dieses Attribut ist <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>.  
  
 `[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]`  
  
 `public class CalculatorService : ICalculatorSession`  
  
 `{//Implement calculator service methods.}`  
  
 In der folgenden Tabelle wird gezeigt, wie die Einstellung des anwendungsweiten Kompatibilitätsmodus mit der vom jeweiligen Dienst angegebenen Unterstützungsebene interagiert:  
  
|Anwendungsweite Einstellung des Kompatibilitätsmodus|[AspNetCompatibilityRequirementsMode]<br /><br /> Einstellung|Beobachtetes Ergebnis|  
|--------------------------------------------------|---------------------------------------------------------|---------------------|  
|AspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Dienst wird erfolgreich aktiviert.|  
|AspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|Dienst wird erfolgreich aktiviert.|  
|AspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Ein Aktivierungsfehler tritt auf, wenn der Dienst eine Nachricht empfängt.|  
|AspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Ein Aktivierungsfehler tritt auf, wenn der Dienst eine Nachricht empfängt.|  
|AspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|Dienst wird erfolgreich aktiviert.|  
|AspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Dienst wird erfolgreich aktiviert.|  
  
> [!NOTE]
>  IIS 7.0 und WAS können WCF-Dienste über andere Protokolle als HTTP zu kommunizieren. WCF-Dienste in Anwendungen, die ASP.NET-Kompatibilitätsmodus aktiviert haben, sind jedoch nicht zulässig, um nicht-HTTP-Endpunkte verfügbar zu machen. Eine solche Konfiguration generiert eine Aktivierungsausnahme, wenn der Dienst seine erste Nachricht empfängt.  
  
 Weitere Informationen zum Aktivieren der ASP.NET-Kompatibilitätsmodus für WCF-Dienste finden Sie unter <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> und [ASP.NET-Kompatibilität](../../../../docs/framework/wcf/samples/aspnet-compatibility.md) Beispiel.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>  
 [Windows Server AppFabric-Hostingfunktionen](http://go.microsoft.com/fwlink/?LinkId=201276)
