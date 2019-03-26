---
title: WCF-Dienste und ASP.NET
ms.date: 03/30/2017
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
ms.openlocfilehash: 80f4f9a473f223928981ee3f0c2e9f2464cbafaf
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463474"
---
# <a name="wcf-services-and-aspnet"></a>WCF-Dienste und ASP.NET

In diesem Thema wird erläutert, hosting Windows Communication Foundation (WCF) Services Seite-an-Seite mit ASP.NET und sie im ASP.NET-Kompatibilitätsmodus gehostet werden.

## <a name="hosting-wcf-side-by-side-with-aspnet"></a>Hosten von WCF-Seite-an-Seite mit ASP.NET

In IIS (Internetinformationsdienste) gehosteten WCF-Dienste können mit gespeichert werden. ASPX-Seiten und ASMX-Webdiensten innerhalb einer einzelnen, gemeinsamen Anwendungsdomäne. ASP.NET bietet allgemeine Infrastrukturdienste, wie etwa AppDomain-Verwaltung und dynamische Kompilierung für WCF und ASP.NET HTTP-Laufzeit. Die Standardkonfiguration für WCF wird Seite-an-Seite mit ASP.NET.

![Screenshot der WCF-Dienste und ASP.NET:: Freigeben des Status.](./media/wcf-services-and-aspnet/windows-communication-foundation-services-asp-dotnet-configuration.gif)

Die ASP.NET HTTP-Laufzeit behandelt ASP.NET-Anforderungen, jedoch nicht Teil bei der Verarbeitung von Anforderungen, die für WCF-Diensten bestimmt ist, obwohl diese Dienste in derselben AppDomain gehostet werden, da ASP.NET Inhalt ist. Stattdessen wird das WCF-Dienstmodell fängt Nachrichten, WCF-Dienste und leitet sie durch die WCF-Transport-/Kanalstapel.

Die Ergebnisse des parallelen Modells sind folgende:

- ASP.NET und WCF-Dienste können die AppDomain-Zustand gemeinsam nutzen. Da die beiden Frameworks in derselben AppDomain koexistieren können, kann WCF AppDomain-Zustand auch mit ASP.NET (einschließlich statischen Variablen, Ereignisse usw.) freigeben.

- WCF-Dienste Verhalten konsistent und unabhängig von hostumgebung und Transport. Die ASP.NET-HTTP-Laufzeit ist absichtlich an IIS/ASP.NET-Hostumgebung und HTTP-Kommunikation gekoppelt. Im Gegensatz dazu wurde WCF entwickelt, für konsistentes Verhalten in Hostumgebungen (WCF verhält sich konsistent, beide innerhalb und außerhalb von IIS) und für Transporte (ein Diensts in IIS 7.0 gehostet und höher verhält sich konsistent auf alle Endpunkte, die sie verfügbar macht, auch wenn Einige dieser Endpunkte verwenden anderer Protokolle als HTTP).

- Innerhalb einer AppDomain gelten die Features, die von der HTTP-Laufzeit implementiert ASP.NET-Inhalt, aber nicht für WCF. Viele HTTP-spezifischen Funktionen der ASP.NET-Anwendungsplattform gelten nicht für WCF-Dienste gehostet in einer AppDomain, die ASP.NET-Inhalt enthält. Im Folgenden sind Beispiele für diese Funktionen aufgeführt:

    - HttpContext: <xref:System.Web.HttpContext.Current%2A> ist immer `null` Wenn der Zugriff innerhalb eines WCF-Diensts. Verwenden Sie stattdessen <xref:System.ServiceModel.Channels.RequestContext>.

    - Dateibasierte Autorisierung: Das WCF-Sicherheitsmodell lässt sich nicht für die Zugriffssteuerungsliste (ACL) auf die SVC-Datei des Diensts angewendet werden, bei der Entscheidung, ob eine dienstanforderung autorisiert ist.

    - Konfigurationsbasierte URL-Autorisierung: Modell der WCF-Sicherheit auf ähnliche Weise nicht erfüllen, in der von "System.Web" angegebene URL-basierten Autorisierungsregeln \<Authorization >-Konfigurationselement. Diese Einstellungen werden für WCF-Anforderungen ignoriert, wenn ein Dienst in einem URL-Bereich von ASP gesichert befindet. NET URL-Autorisierungsregeln.

    - HttpModule-Erweiterbarkeit: Der WCF-Hostinginfrastruktur abgefangen WCF anfordert, wenn die <xref:System.Web.HttpApplication.PostAuthenticateRequest> Ereignis wird ausgelöst, und die Verarbeitung nicht an die ASP.NET HTTP-Pipeline zurück. Module, die zum Abfangen von Anforderungen in späteren Phasen der Pipeline codiert sind werden WCF-Anforderungen nicht abgefangen werden.

    - ASP.NET-Identitätswechsel: In der Standardeinstellung WCF-Anforderungen ausgeführt als die IIS Prozessidentität, auch wenn für ASP.NET Identitätswechsel unter Verwendung von "System.Web" aktivieren \<Identity impersonate = "true" / > Konfigurationsoption.

Diese Einschränkungen gelten nur für in IIS gehostete WCF-Dienste. Das Verhalten des ASP.NET-Inhalts wird durch das Vorhandensein von WCF nicht beeinflusst.

WCF-Anwendungen, die üblicherweise von der HTTP-Pipeline bereitgestellte Funktionalität benötigen sollten mithilfe der WCF-Entsprechungen, Host und transport unabhängig:

- <xref:System.ServiceModel.OperationContext> anstelle von <xref:System.Web.HttpContext>.

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> statt der Datei-/URL-Autorisierung von ASP.NET.

- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> oder benutzerdefinierte überlagerte Kanäle statt der HTTP-Module.

- Identitätswechsel für jeden Vorgang, der anstelle von WCF System.Web-Identitätswechsels.

Alternativ können Sie erwägen, Ihre Dienste im ASP.NET-Kompatibilitätsmodus von WCF ausgeführt.

## <a name="hosting-wcf-services-in-aspnet-compatibility-mode"></a>Hosten von WCF-Diensten im ASP.NET-Kompatibilitätsmodus

Obwohl die WCF-Dienstmodells für konsistentes Verhalten in Hostumgebungen und für Transporte konzipiert ist, sind doch Szenarien häufig, in denen eine Anwendung dieses Maß an Flexibilität nicht erforderlich ist. ASP.NET-Kompatibilitätsmodus von WCF eignet sich für Szenarien, die erfordern nicht die Möglichkeit des Hostens außerhalb von IIS oder über andere Protokolle als HTTP zu kommunizieren, aber die Verwendung aller Funktionen der ASP.NET-Webanwendungsplattform.

Im Gegensatz zu der Seite-an-Seite-Standardkonfiguration, in dem die WCF-hosting-Infrastruktur fängt der WCF-Nachrichten ab und leitet sie aus der HTTP-Pipeline, beteiligt WCF-Dienste im ASP.NET-Kompatibilitätsmodus, voll am ASP.NET HTTP-Anforderungslebenszyklus. Im Kompatibilitätsmodus verwenden WCF-Dienste den HTTP-Pipeline über eine <xref:System.Web.IHttpHandler> Implementierung ähnlich der Weise, wie Anforderungen für ASPX-Seiten und ASMX-Webdienste behandelt werden. Folglich verhält sich WCF genau wie ASMX in Bezug auf die folgenden ASP.NET-Funktionen:

- <xref:System.Web.HttpContext>: WCF-Dienste im ASP.NET-Kompatibilitätsmodus ausgeführt, können auf zugreifen <xref:System.Web.HttpContext.Current%2A> und den zugehörigen Status.

- Dateibasierte Autorisierung: WCF-Dienste im ASP.NET-Kompatibilitätsmodus ausgeführt, können sicher sein, durch die Zugriffssteuerungslisten (ACLs) für Datei-System auf die SVC Datei anfügen.

- Konfigurierbare URL-Autorisierung: ASP. NET URL-Autorisierungsregeln werden für WCF-Anforderungen erzwungen, wenn der WCF-Dienst im ASP.NET-Kompatibilitätsmodus ausgeführt wird.

- <xref:System.Web.HttpModuleCollection> Erweiterbarkeit: Da WCF-Dienste im ASP.NET-Kompatibilitätsmodus, voll am ASP.NET HTTP-Anforderungslebenszyklus teilnehmen, ist HTTP-Modul, das in der HTTP-Pipeline konfigurierten WCF-Anforderungen vor und nach dem Dienstaufruf arbeiten.

- ASP.NET-Identitätswechsel: Führen Sie mit der aktuellen Identität, die der WCF-Dienste mit Identitätswechsel Thread, der die IIS-Prozessidentität unterscheiden sein kann, wenn ASP.NET-Identitätswechsel für die Anwendung aktiviert wurde. Wenn Identitätswechsel in ASP.NET und WCF-Identitätswechsel für einen bestimmten Dienstvorgang aktiviert sind, die dienstimplementierung letztlich unter der Identität ausgeführt von WCF abgerufen.

ASP.NET-Kompatibilitätsmodus von WCF erfolgt auf der Anwendungsebene über die folgende Konfiguration (befindet sich in der Datei "Web.config" der Anwendung):

```xml
<system.serviceModel>
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```

Dieser Wert standardmäßig auf "`true`" nicht angegeben. Wenn dieser Wert auf "`false`" gibt an, dass alle WCF-Dienste, die in der Anwendung ausgeführt wird, nicht im ASP.NET-Kompatibilitätsmodus ausgeführt werden.

Da der ASP.NET-Kompatibilitätsmodus Semantik der anforderungsverarbeitung impliziert, die grundlegend von der WCF-Standard sind, haben einzelnen dienstimplementierungen die Möglichkeit, um zu steuern, ob die Ausführung innerhalb einer Anwendung für die ASP.NET Im Kompatibilitätsmodus wurde aktiviert. Dienste können das <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> verwenden, um anzugeben, ob sie den ASP.NET-Kompatibilitätsmodus unterstützen. Der Standardwert für dieses Attribut ist <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>.

```csharp
[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
public class CalculatorService : ICalculatorSession
{//Implement calculator service methods.}
```

In der folgenden Tabelle wird gezeigt, wie die Einstellung des anwendungsweiten Kompatibilitätsmodus mit der vom jeweiligen Dienst angegebenen Unterstützungsebene interagiert:

|Anwendungsweite Einstellung des Kompatibilitätsmodus|[AspNetCompatibilityRequirementsMode]<br /><br /> Einstellung|Beobachtetes Ergebnis|
|--------------------------------------------------|---------------------------------------------------------|---------------------|
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Dienst wird erfolgreich aktiviert.|
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|Dienst wird erfolgreich aktiviert.|
|aspNetCompatibilityEnabled = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Ein Aktivierungsfehler tritt auf, wenn der Dienst eine Nachricht empfängt.|
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Ein Aktivierungsfehler tritt auf, wenn der Dienst eine Nachricht empfängt.|
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|Dienst wird erfolgreich aktiviert.|
|aspNetCompatibilityEnabled = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Dienst wird erfolgreich aktiviert.|

> [!NOTE]
> IIS 7.0 und WAS können WCF-Dienste über andere Protokolle als HTTP zu kommunizieren. WCF-Dienste in Anwendungen, die ASP.NET-Kompatibilitätsmodus aktiviert haben, sind jedoch nicht zulässig, um nicht-HTTP-Endpunkte verfügbar zu machen. Eine solche Konfiguration generiert eine Aktivierungsausnahme, wenn der Dienst seine erste Nachricht empfängt.

Weitere Informationen zum Aktivieren des ASP.NET-Kompatibilitätsmodus für WCF-Dienste finden Sie unter <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> und [ASP.NET-Kompatibilität](../samples/aspnet-compatibility.md) Beispiel.

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>
- [Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))