---
title: Unterstützte Bereitstellungsszenarien
ms.date: 03/30/2017
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
ms.openlocfilehash: 299c8f2e29806a123e0a8b6e1e70d8cc13daa7bf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546249"
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

Viele kommerzielle Anbieter von ASP.NET-Webanwendungs-Hostingdiensten legen fest, dass Anwendungen, die auf Ihren Servern ausgeführt werden, mit dem Berechtigungs Satz "ASP.NET 2,0 WCF-Dienste können in diesen Umgebungen ausgeführt werden, sofern Sie die <xref:System.ServiceModel.BasicHttpBinding> , die <xref:System.ServiceModel.WebHttpBinding> oder die <xref:System.ServiceModel.WSHttpBinding> mit Sicherheit auf Transport Ebene verwenden.

WCF-Dienste, die in Host Umgebungen mit mittlerer Vertrauenswürdigkeit ausgeführt werden, können auch als Dienste der mittleren Ebene fungieren, indem Nachrichten als Reaktion auf Client Anforderungen an andere Server gesendet werden. Szenarien der mittleren Ebene werden auf dem Server unterstützt, wenn die Hostumgebung der Anwendung die geeignete <xref:System.Net.WebPermission> gewährt hat, damit diese ausgehende Anforderungen an den gewünschten Server senden kann.

Zusätzlich zu SOAP-Messaging, das eine der unterstützten SOAP-Bindungen verwendet, unterstützt WCF das <xref:System.ServiceModel.WebHttpBinding> zum Entwickeln von Webdiensten in teilweise vertrauenswürdigen Anwendungen. Die WCF- [Web-http-Programmier Modelle](wcf-web-http-programming-model.md), [WCF-Syndikation](wcf-syndication.md)und [AJAX-Integration und JSON-Unterstützung](ajax-integration-and-json-support.md) von WCF werden bei teilweiser Vertrauenswürdigkeit unterstützt.

Workflowdienste erfordern die Berechtigung "Volles Vertrauen" und können nicht in teilweise vertrauenswürdigen Anwendungen verwendet werden.

Weitere Informationen finden Sie unter Gewusst [wie: Verwenden von mittlerer Vertrauenswürdigkeit in ASP.NET 2,0](/previous-versions/msp-n-p/ff648344(v=pandp.10)).

## <a name="partial-trust-on-the-client"></a>Teilweise Vertrauenswürdigkeit auf dem Client

Bestimmte Sicherheitsvorkehrungen müssen getroffen werden, wenn Code von nicht vertrauenswürdigen Internetsites heruntergeladen oder ausgeführt wird. Sowohl die [ClickOnce-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment) als auch die XBAP-Technologie (XAML Browser Application) von WPF nutzen teilweise Vertrauenswürdigkeit, um nicht vertrauenswürdigem Code eingeschränkte Berechtigungen (Internet Zone) zu gewähren.

WCF kann verwendet werden, um über teilweise vertrauenswürdige Anwendungen, die von der [ClickOnce-Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment) oder XBAP bereitgestellt wurden, mit Remote Servern zu kommunizieren. Der Berechtigungs Satz für die Internet Zone enthält <xref:System.Net.WebPermission> für den Ursprungs Host, der es diesen Anwendungen ermöglicht, mit Ihrem Ursprungsserver zu kommunizieren, indem Sie eine [Partial Trust Feature Compatibility](partial-trust-feature-compatibility.md)der unterstützten WCF-Bindungen verwenden.

## <a name="see-also"></a>Siehe auch

- [Codezugriffssicherheit](../../misc/code-access-security.md)
- [Übersicht über Browser-gehostete Anwendungen in Windows Presentation Foundation](/dotnet/desktop/wpf/app-development/wpf-xaml-browser-applications-overview)
- [Teilweise Vertrauenswürdigkeit](partial-trust.md)
- [ASP.net-Vertrauens Ebenen und-Richtlinien Dateien](/previous-versions/wyts434y(v=vs.140))
