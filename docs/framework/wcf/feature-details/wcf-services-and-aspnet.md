---
title: WCF-Dienste und ASP.net
ms.date: 03/30/2017
ms.assetid: b980496a-f0b0-4319-8e55-a0f0fa32da70
ms.openlocfilehash: 0a64e277d3465b77a2553d6b9c3901f09a6e1a52
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2019
ms.locfileid: "75544740"
---
# <a name="wcf-services-and-aspnet"></a>WCF-Dienste und ASP.net

In diesem Thema wird das parallele Hosting von Windows Communication Foundation-Diensten (WCF) mit ASP.net und das Hosting im ASP.NET-Kompatibilitätsmodus erläutert.

## <a name="hosting-wcf-side-by-side-with-aspnet"></a>Paralleles Hosting von WCF mit ASP.net

In Internetinformationsdienste (IIS) gehostete WCF-Dienste können mit gefunden werden. ASPX-Seiten und ASMX-Webdienste innerhalb einer einzelnen, allgemeinen Anwendungsdomäne. ASP.net bietet allgemeine Infrastrukturdienste, wie z. b. die AppDomain-Verwaltung und die dynamische Kompilierung für WCF und die ASP.NET HTTP-Laufzeit. Die Standardkonfiguration für WCF ist parallel zu ASP.net.

![Screenshot der WCF-Dienste und ASP .net: Freigabe Status](./media/wcf-services-and-aspnet/windows-communication-foundation-services-asp-dotnet-configuration.gif)

Die ASP.NET-HTTP-Laufzeit verarbeitet ASP.NET-Anforderungen, ist jedoch nicht an der Verarbeitung von Anforderungen beteiligt, die für WCF-Dienste bestimmt sind, auch wenn diese Dienste in derselben AppDomain gehostet werden wie der ASP.net-Inhalt. Stattdessen fängt das WCF-Dienstmodell Nachrichten ab, die an WCF-Dienste adressiert sind, und leitet Sie durch den WCF-Transport-/Kanalstapel.

Die Ergebnisse des parallelen Modells sind folgende:

- Die ASP.net-und WCF-Dienste können den AppDomain-Zustand freigeben. Da die beiden Frameworks in derselben AppDomain nebeneinander vorhanden sein können, kann WCF auch den AppDomain-Zustand mit ASP.net (einschließlich statischer Variablen, Ereignisse usw.) freigeben.

- WCF-Dienste Verhalten sich konsistent, unabhängig von der Host Umgebung und dem Transport. Die ASP.NET-HTTP-Laufzeit ist absichtlich an IIS/ASP.NET-Hostumgebung und HTTP-Kommunikation gekoppelt. Im Gegensatz dazu ist WCF für das konsistente Verhalten in Host Umgebungen konzipiert (WCF verhält sich sowohl innerhalb als auch außerhalb von IIS konsistent) und übertragen (ein Dienst, der in IIS 7,0 und höher gehostet wird, verfügt über ein konsistentes Verhalten in allen Endpunkten, die es verfügbar macht, auch für einige dieser Endpunkte werden andere Protokolle als HTTP verwendet.)

- In einer AppDomain gelten die von der HTTP-Laufzeit implementierten Funktionen für ASP.net-Inhalt, jedoch nicht für WCF. Viele HTTP-spezifische Features der ASP.NET-Anwendungsplattform gelten nicht für WCF-Dienste, die in einer AppDomain gehostet werden, die ASP.net-Inhalt enthält. Im Folgenden sind Beispiele für diese Funktionen aufgeführt:

  - HttpContext: <xref:System.Web.HttpContext.Current%2A> immer `null`, wenn von einem WCF-Dienst aus darauf zugegriffen wird. Verwenden Sie stattdessen <xref:System.ServiceModel.Channels.RequestContext> .

  - Dateibasierte Autorisierung: das WCF-Sicherheitsmodell lässt nicht zu, dass die Zugriffs Steuerungs Liste (ACL) für die SVC-Datei des Diensts angewendet wird, wenn eine Service Request autorisiert ist.

  - Konfigurationsbasierte URL-Autorisierung: auf ähnliche Weise befolgt das WCF-Sicherheitsmodell keine URL-basierten Autorisierungs Regeln, die in der \<Authorization > Configuration-Element von System. Web angegeben sind. Diese Einstellungen werden für WCF-Anforderungen ignoriert, wenn sich ein Dienst in einem durch ASP gesicherten URL-Bereich befindet. Die URL-Autorisierungs Regeln für net.

  - HttpModule-Erweiterbarkeit: die WCF-Hostinginfrastruktur fängt WCF-Anforderungen ab, wenn das <xref:System.Web.HttpApplication.PostAuthenticateRequest>-Ereignis ausgelöst wird, und gibt keine Verarbeitung an die ASP.NET-HTTP-Pipeline zurück. Module, die zum Abfangen von Anforderungen in späteren Phasen der Pipeline programmiert sind, fangen keine WCF-Anforderungen ab.

  - ASP.NET-Identitätswechsel: Standardmäßig werden WCF-Anforderungen immer als IIS-Prozess Identität ausgeführt, auch wenn ASP.net so festgelegt ist, dass der Identitätswechsel mithilfe von System. Web aktiviert ist, \<Identity Identitätswechsel = "true"/> Konfigurationsoption.

Diese Einschränkungen gelten nur für WCF-Dienste, die in der IIS-Anwendung gehostet werden. Das Verhalten von ASP.net-Inhalten wird durch das vorhanden sein von WCF nicht beeinträchtigt.

WCF-Anwendungen, die Funktionen erfordern, die traditionell von der HTTP-Pipeline bereitgestellt werden, sollten die Verwendung der WCF-Entsprechungen in Erwägung gezogen werden, die von

- <xref:System.ServiceModel.OperationContext> anstelle von <xref:System.Web.HttpContext>.

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> statt der Datei-/URL-Autorisierung von ASP.NET.

- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> oder benutzerdefinierte überlagerte Kanäle statt der HTTP-Module.

- Identitätswechsel für jeden Vorgang, der WCF anstelle von System. Web-Identitätswechsel verwendet.

Alternativ können Sie die Ausführung ihrer Dienste im ASP.NET-Kompatibilitätsmodus von WCF in Erwägung gezogen.

## <a name="hosting-wcf-services-in-aspnet-compatibility-mode"></a>Hosting von WCF-Diensten im ASP.NET-Kompatibilitätsmodus

Obwohl das WCF-Modell für das konsistente Verhalten in Host Umgebungen und Transporten konzipiert ist, gibt es häufig Szenarios, in denen eine Anwendung diesen Grad an Flexibilität nicht benötigt. Der ASP.NET-Kompatibilitätsmodus von WCF eignet sich für Szenarien, die nicht die Möglichkeit zum Hosten außerhalb von IIS oder zur Kommunikation über andere Protokolle als http benötigen, aber alle Funktionen der Webanwendungs Plattform ASP.NET verwenden.

Anders als bei der standardmäßigen parallelen Konfiguration, bei der die WCF-Hostinginfrastruktur WCF-Nachrichten abfängt und Sie aus der HTTP-Pipeline leitet, nehmen WCF-Dienste, die im ASP.NET-Kompatibilitätsmodus ausgeführt werden, vollständig im ASP.NET HTTP-Anforderungs Lebenszyklus Teil Im Kompatibilitätsmodus verwenden WCF-Dienste die HTTP-Pipeline über eine <xref:System.Web.IHttpHandler>-Implementierung, ähnlich der Art und Weise, wie Anforderungen für ASPX-Seiten und ASMX-Webdienste verarbeitet werden. Infolgedessen verhält sich WCF in Bezug auf die folgenden ASP.NET-Funktionen identisch mit ASMX:

- <xref:System.Web.HttpContext>: WCF-Dienste, die im ASP.NET-Kompatibilitätsmodus ausgeführt werden, können auf <xref:System.Web.HttpContext.Current%2A> und den zugehörigen Zustand zugreifen

- Dateibasierte Autorisierung: WCF-Dienste, die im ASP.NET-Kompatibilitätsmodus ausgeführt werden, können sicher sein, indem Sie der SVC-Datei des Diensts Dateisystem-Zugriffs Steuerungs Listen (ACLs) anfügen.

- Konfigurierbare URL-Autorisierung: ASP. Die URL-Autorisierungs Regeln von NET werden für WCF-Anforderungen erzwungen, wenn der WCF-Dienst im ASP.NET-Kompatibilitätsmodus ausgeführt wird.

- <xref:System.Web.HttpModuleCollection> Erweiterbarkeit: da WCF-Dienste, die im ASP.NET-Kompatibilitätsmodus ausgeführt werden, vollständig im ASP.NET HTTP-Anforderungs Lebenszyklus teilnehmen, kann jedes in der HTTP-Pipeline konfigurierte HTTP-Modul sowohl vor als auch nach dem Dienst Aufruf auf WCF-Anforderungen angewendet werden.

- ASP.NET-Identitätswechsel: WCF-Dienste werden mithilfe der aktuellen Identität des Thread mit ASP.net-Identität ausgeführt, der sich von der IIS-Prozess Identität unterscheiden kann, wenn ASP.NET-Identitätswechsel für die Anwendung aktiviert wurde. Wenn ASP.NET-Identitätswechsel und WCF-Identitätswechsel für einen bestimmten Dienst Vorgang aktiviert sind, wird die Dienst Implementierung letztendlich mit der aus WCF erhaltenen Identität ausgeführt.

Der ASP.NET-Kompatibilitätsmodus von WCF wird auf Anwendungsebene durch die folgende Konfiguration aktiviert (in der Datei "Web. config" der Anwendung):

```xml
<system.serviceModel>
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```

Dieser Wert wird standardmäßig `false`, wenn nicht angegeben. Der Wert `false` gibt an, dass alle WCF-Dienste, die in der Anwendung ausgeführt werden, nicht im ASP.NET-Kompatibilitätsmodus ausgeführt werden.

Da der ASP.NET-Kompatibilitätsmodus eine Semantik der Anforderungs Verarbeitung impliziert, die sich grundlegend vom WCF-Standard unterscheidet, haben einzelne Dienst Implementierungen die Möglichkeit, zu steuern, ob Sie in einer Anwendung ausgeführt werden, für die ASP.net Der Kompatibilitätsmodus wurde aktiviert. Dienste können das <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> verwenden, um anzugeben, ob sie den ASP.NET-Kompatibilitätsmodus unterstützen. Der Standardwert für dieses Attribut ist <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>.

```csharp
[AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
public class CalculatorService : ICalculatorSession
{//Implement calculator service methods.}
```

In der folgenden Tabelle wird gezeigt, wie die Einstellung des anwendungsweiten Kompatibilitätsmodus mit der vom jeweiligen Dienst angegebenen Unterstützungsebene interagiert:

|Anwendungsweite Einstellung des Kompatibilitätsmodus|[AspNetCompatibilityRequirementsMode]<br /><br /> -Einstellung|Beobachtetes Ergebnis|
|--------------------------------------------------|---------------------------------------------------------|---------------------|
|aspnetcompatibilityaktivierte = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Dienst wird erfolgreich aktiviert.|
|aspnetcompatibilityaktivierte = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|Dienst wird erfolgreich aktiviert.|
|aspnetcompatibilityaktivierte = "`true`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Ein Aktivierungsfehler tritt auf, wenn der Dienst eine Nachricht empfängt.|
|aspnetcompatibilityaktivierte = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>|Ein Aktivierungsfehler tritt auf, wenn der Dienst eine Nachricht empfängt.|
|aspnetcompatibilityaktivierte = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed>|Dienst wird erfolgreich aktiviert.|
|aspnetcompatibilityaktivierte = "`false`"|<xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.NotAllowed>|Dienst wird erfolgreich aktiviert.|

> [!NOTE]
> IIS 7,0 und was ermöglicht WCF-Diensten, über andere Protokolle als http zu kommunizieren. WCF-Dienste, die in Anwendungen ausgeführt werden, bei denen der ASP.NET-Kompatibilitätsmodus aktiviert ist, dürfen jedoch keine nicht-HTTP-Endpunkte verfügbar machen. Eine solche Konfiguration generiert eine Aktivierungsausnahme, wenn der Dienst seine erste Nachricht empfängt.

Weitere Informationen zum Aktivieren des ASP.NET-Kompatibilitätsmodus für WCF-Dienste finden Sie unter <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> und das [ASP.NET Compatibility](../samples/aspnet-compatibility.md) -Beispiel.

## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>
- [Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
