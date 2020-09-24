---
title: Azure Active Directory
description: Architektur von Cloud Native .net-apps für Azure | Azure Active Directory
ms.date: 06/30/2019
ms.openlocfilehash: 55787f3565fc15bb25cf1a101aa5c1e3ddefe5e7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161112"
---
# <a name="azure-active-directory"></a><span data-ttu-id="5c300-103">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5c300-103">Azure Active Directory</span></span>

<span data-ttu-id="5c300-104">Microsoft Azure Active Directory (Azure AD) bietet Identitäts-und Zugriffs Verwaltung als Dienst.</span><span class="sxs-lookup"><span data-stu-id="5c300-104">Microsoft Azure Active Directory (Azure AD) offers identity and access management as a service.</span></span> <span data-ttu-id="5c300-105">Kunden verwenden Sie, um zu konfigurieren und zu warten, wer Benutzer sind, welche Informationen über Sie gespeichert werden, wer auf diese Informationen zugreifen kann, wer Sie verwalten kann und auf welche apps Sie zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="5c300-105">Customers use it to configure and maintain who users are, what information to store about them, who can access that information, who can manage it, and what apps can access it.</span></span> <span data-ttu-id="5c300-106">Aad kann Benutzer für Anwendungen authentifizieren, die für die Verwendung konfiguriert sind, und bietet eine Single Sign-on (SSO).</span><span class="sxs-lookup"><span data-stu-id="5c300-106">AAD can authenticate users for applications configured to use it, providing a single sign-on (SSO) experience.</span></span> <span data-ttu-id="5c300-107">Sie kann eigenständig verwendet oder in Windows AD integriert werden, das lokal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5c300-107">It can be used on its own or be integrated with Windows AD running on premises.</span></span>

<span data-ttu-id="5c300-108">Azure AD für die Cloud erstellt.</span><span class="sxs-lookup"><span data-stu-id="5c300-108">Azure AD is built for the cloud.</span></span> <span data-ttu-id="5c300-109">Es handelt sich tatsächlich um eine cloudbasierte Identitäts Lösung, die eine Rest-basierte Graph-API und odata-Syntax für Abfragen verwendet, anders als Windows AD, bei dem LDAP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c300-109">It's truly a cloud-native identity solution that uses a REST-based Graph API and OData syntax for queries, unlike Windows AD, which uses LDAP.</span></span> <span data-ttu-id="5c300-110">Lokale Active Directory können Benutzerattribute mithilfe von Identitäts Synchronisierungs Diensten in der Cloud synchronisieren, sodass die gesamte Authentifizierung mithilfe Azure AD in der Cloud erfolgen kann.</span><span class="sxs-lookup"><span data-stu-id="5c300-110">On premises Active Directory can sync user attributes to the cloud using Identity Sync Services, allowing all authentication to take place in the cloud using Azure AD.</span></span> <span data-ttu-id="5c300-111">Alternativ kann die Authentifizierung über Connect konfiguriert werden, um Sie über AD FS zurück an lokale Active Directory zu übergeben, um von Windows AD lokal abgeschlossen zu werden.</span><span class="sxs-lookup"><span data-stu-id="5c300-111">Alternately, authentication can be configured via Connect to pass back to local Active Directory via ADFS to be completed by Windows AD on premises.</span></span>

<span data-ttu-id="5c300-112">Azure Ad unterstützt Unternehmens Branding-Anmelde Bildschirme, Multi-Factory-Authentifizierung und cloudbasierte Anwendungs Proxys, die verwendet werden, um SSO für Lokal gehostete Anwendungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="5c300-112">Azure AD supports company branded sign-in screens, multi-factory authentication, and cloud-based application proxies that are used to provide SSO for applications hosted on premises.</span></span> <span data-ttu-id="5c300-113">Sie bietet verschiedene Arten von Sicherheitsberichten und Warnungs Funktionen.</span><span class="sxs-lookup"><span data-stu-id="5c300-113">It offers different kinds of security reporting and alert capabilities.</span></span>

## <a name="references"></a><span data-ttu-id="5c300-114">References</span><span class="sxs-lookup"><span data-stu-id="5c300-114">References</span></span>

- [<span data-ttu-id="5c300-115">Microsoft Identity Platform</span><span class="sxs-lookup"><span data-stu-id="5c300-115">Microsoft identity platform</span></span>](/azure/active-directory/develop/)

>[!div class="step-by-step"]
><span data-ttu-id="5c300-116">[Zurück](authentication-authorization.md)
>[Weiter](identity-server.md)</span><span class="sxs-lookup"><span data-stu-id="5c300-116">[Previous](authentication-authorization.md)
[Next](identity-server.md)</span></span>
