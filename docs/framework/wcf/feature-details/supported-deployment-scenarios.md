---
title: Unterstützte Bereitstellungsszenarien
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 5be9ab3d300da2095a45846d334512382b4067f6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743447"
---
# <a name="supported-deployment-scenarios"></a>Unterstützte Bereitstellungsszenarien

Die Teilmenge der Windows Communication Foundation (WCF)-Funktionen, die für die Verwendung in teilweise vertrauenswürdigen Anwendungen unterstützt werden, ist so konzipiert, dass Sie die Anforderungen einiger, aber nicht aller Szenarien für die Verwendung von WCF erfüllen. Auf dem-Server erfüllt WCF die Anforderungen von freigegebenen Hostinganbietern auf Internet Ebene, die aus Sicherheitsgründen Anwendungen von Drittanbietern mit dem Berechtigungs Satz ASP.NET 2,0-mittlerer Vertrauensstellung ausführen. Auf dem Client ist die Unterstützung für teilweise vertrauenswürdige WCF-Dienste für die Anforderungen von Bereitstellungs Technologien wie der [ClickOnce-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment) oder der XAML-Browser-Anwendungs Technologie von WPF konzipiert, die eine nahtlose und sichere Bereitstellung von Desktop Anwendungen von nicht vertrauenswürdigen Sites ermöglichen.

## <a name="minimum-permission-requirements"></a>Mindestanforderungen für Berechtigungen

WCF unterstützt eine Teilmenge von Funktionen in Anwendungen, die unter einem der folgenden benannten Standard Berechtigungs Sätze ausgeführt werden:

- Berechtigungen für mittlere Vertrauenswürdigkeit

- Internetzonenberechtigungen

Der Versuch, WCF in teilweise vertrauenswürdigen Anwendungen mit restriktiveren Berechtigungen zu verwenden, kann zur Laufzeit zu Sicherheits Ausnahmen führen.

Weitere Informationen zu den verschiedenen Funktionen, die von diesen Berechtigungssätzen unterstützt werden, finden Sie unter [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md).

## <a name="partial-trust-on-the-server"></a>Teilweise Vertrauenswürdigkeit auf dem Server

Viele kommerzielle Anbieter von ASP.NET-Webanwendungs-Hostingdiensten legen fest, dass Anwendungen, die auf Ihren Servern ausgeführt werden, mit dem Berechtigungs Satz "ASP.NET 2,0 WCF-Dienste können in diesen Umgebungen ausgeführt werden, sofern Sie die <xref:System.ServiceModel.BasicHttpBinding>, die <xref:System.ServiceModel.WebHttpBinding>oder die <xref:System.ServiceModel.WSHttpBinding> mit Sicherheit auf Transport Ebene verwenden.

WCF-Dienste, die in Host Umgebungen mit mittlerer Vertrauenswürdigkeit ausgeführt werden, können auch als Dienste der mittleren Ebene fungieren, indem Nachrichten als Reaktion auf Client Anforderungen an andere Server gesendet werden. Szenarien der mittleren Ebene werden auf dem Server unterstützt, wenn die Hostumgebung der Anwendung die geeignete <xref:System.Net.WebPermission> gewährt hat, damit diese ausgehende Anforderungen an den gewünschten Server senden kann.

Zusätzlich zu SOAP-Messaging, das eine der unterstützten SOAP-Bindungen verwendet, unterstützt WCF die <xref:System.ServiceModel.WebHttpBinding> zum Entwickeln von Webdiensten in teilweise vertrauenswürdigen Anwendungen. Die WCF- [Web-http-Programmier Modelle](wcf-web-http-programming-model.md), [WCF-Syndikation](wcf-syndication.md)und [AJAX-Integration und JSON-Unterstützung](ajax-integration-and-json-support.md) von WCF werden bei teilweiser Vertrauenswürdigkeit unterstützt.

Workflowdienste erfordern die Berechtigung "Volles Vertrauen" und können nicht in teilweise vertrauenswürdigen Anwendungen verwendet werden.

Weitere Informationen finden Sie unter Gewusst [wie: Verwenden von mittlerer Vertrauenswürdigkeit in ASP.NET 2,0](https://docs.microsoft.com/previous-versions/msp-n-p/ff648344(v=pandp.10)).

## <a name="partial-trust-on-the-client"></a>Teilweise Vertrauenswürdigkeit auf dem Client

Bestimmte Sicherheitsvorkehrungen müssen getroffen werden, wenn Code von nicht vertrauenswürdigen Internetsites heruntergeladen oder ausgeführt wird. Sowohl die [ClickOnce-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment) als auch die XBAP-Technologie (XAML Browser Application) von WPF nutzen teilweise Vertrauenswürdigkeit, um nicht vertrauenswürdigem Code eingeschränkte Berechtigungen (Internet Zone) zu gewähren.

WCF kann verwendet werden, um über teilweise vertrauenswürdige Anwendungen, die von der [ClickOnce-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment) oder XBAP bereitgestellt wurden, mit Remote Servern zu kommunizieren. Der Berechtigungs Satz für die Internet Zone umfasst <xref:System.Net.WebPermission> für den Ursprungs Host, der es diesen Anwendungen ermöglicht, mit Ihrem Ursprungsserver zu kommunizieren, indem Sie eine der in der [Kompatibilität mit Teil vertrauenswürdigen Funktionen](partial-trust-feature-compatibility.md)beschriebenen unterstützten WCF-Bindungen verwenden

## <a name="see-also"></a>Weitere Informationen

- [Codezugriffssicherheit](../../misc/code-access-security.md)
- [Übersicht über Windows Presentation Foundation Browser gehostete Anwendungen](../../wpf/app-development/wpf-xaml-browser-applications-overview.md)
- [Teilweise Vertrauenswürdigkeit](partial-trust.md)
- [ASP.net-Vertrauens Ebenen und-Richtlinien Dateien](https://docs.microsoft.com/previous-versions/wyts434y(v=vs.140))
