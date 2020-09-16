---
title: 'Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: cec9356467886be022d05ead55d5cb6ccddcd838
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558679"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="79e90-102">Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung</span><span class="sxs-lookup"><span data-stu-id="79e90-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="79e90-103">Dieses Thema enthält einen Überblick über die Schritte zum Aktivieren der Sicherheit auf Nachrichtenebene für den Nachrichtenaustausch innerhalb einer zuverlässigen Sitzung mithilfe einer der vom System bereitgestellten Bindungen, die eine solche Sitzung zwar unterstützen, standardmäßig aber keine Unterstützung dafür bieten.</span><span class="sxs-lookup"><span data-stu-id="79e90-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="79e90-104">Aktivieren Sie eine sichere, zuverlässige Sitzung entweder Imperativ durch die Verwendung von Code oder deklarativ in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="79e90-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="79e90-105">Dieses Verfahren verwendet die Konfigurationsdateien von Client und Dienst, um die sichere, zuverlässige Sitzung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="79e90-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="79e90-106">Dieses Verfahren besteht aus den folgenden drei Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="79e90-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="79e90-107">Angeben, dass der Client und der Dienst Nachrichten in einer zuverlässigen Sitzung austauschen.</span><span class="sxs-lookup"><span data-stu-id="79e90-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="79e90-108">Anfordern der Sicherheit auf Nachrichtenebene innerhalb der zuverlässigen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="79e90-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="79e90-109">Angeben des Clientanmeldeinformationstyps, den der Client verwenden muss, um sich selbst beim Server authentifizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="79e90-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="79e90-110">In der ersten Aufgabe ist es wichtig, dass das Endpunkt Konfigurationselement ein- `bindingConfiguration` Attribut enthält, das auf eine Bindungs Konfiguration mit dem Namen verweist (in diesem Beispiel) `MessageSecurity` .</span><span class="sxs-lookup"><span data-stu-id="79e90-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="79e90-111">Das [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) Konfigurationselement verweist dann auf diesen Namen, um zuverlässige Sitzungen zu aktivieren, indem das- `enabled` Attribut des-Elements auf festgelegt wird [**\<reliableSession>**](/previous-versions/ms731375(v=vs.90)) `true` .</span><span class="sxs-lookup"><span data-stu-id="79e90-111">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](/previous-versions/ms731375(v=vs.90)) element to `true`.</span></span> <span data-ttu-id="79e90-112">Sie können angeben, dass eine Zusicherung der Zustellung in der richtigen Reihenfolge innerhalb einer zuverlässigen Sitzung verfügbar ist, indem Sie das `ordered`-Attribut auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="79e90-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="79e90-113">Die Quell Kopie des Beispiels, auf dem diese Konfigurations Prozedur basiert, finden Sie in der [zuverlässigen WS-Sitzung](../samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="79e90-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="79e90-114">Die wesentlichen Elemente der zweiten Aufgabe werden erreicht, indem das `mode` -Attribut des **\<security>** -Elements, das im **\<binding>** -Element des Clients und des dienstanteils enthalten ist, auf `Message` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="79e90-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="79e90-115">Die wesentlichen Elemente der dritten Aufgabe werden erreicht, indem das `clientCredentialType` -Attribut des **\<message>** -Elements, das im **\<security>** -Element des Clients und des dienstanteils enthalten ist, auf `Certificate` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="79e90-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="79e90-116">Wenn Sie Nachrichten Sicherheit mit zuverlässigen Sitzungen verwenden, versucht zuverlässiges Messaging, einen nicht authentifizierten Client zu authentifizieren, bis ein Timeout auftritt, anstatt beim ersten Fehler eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="79e90-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="79e90-117">Konfigurieren Sie den Dienst mit einer wsHttpBinding, um eine zuverlässige Sitzung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="79e90-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="79e90-118">Dieses Verfahren wird unter Vorgehens [Weise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](how-to-exchange-messages-within-a-reliable-session.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="79e90-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="79e90-119">Konfigurieren des Clients mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung</span><span class="sxs-lookup"><span data-stu-id="79e90-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="79e90-120">Dieses Verfahren wird unter Vorgehens [Weise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](how-to-exchange-messages-within-a-reliable-session.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="79e90-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="79e90-121">Legen Sie den Modus und clientkredentialtype in der Konfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="79e90-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="79e90-122">Fügen Sie dem- [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) Element der Konfigurationsdatei ein entsprechendes Bindungs Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="79e90-122">Add an appropriate binding element to the [**\<bindings>**](../../configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="79e90-123">Im folgenden Beispiel wird ein-Element hinzugefügt [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="79e90-123">The following example adds a [**\<wsHttpBinding>**](../../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="79e90-124">Fügen Sie ein **\<binding>** -Element hinzu, und legen Sie dessen- `name` Attribut auf einen geeigneten Wert fest</span><span class="sxs-lookup"><span data-stu-id="79e90-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="79e90-125">Im Beispiel wird der Name verwendet `MessageSecurity` .</span><span class="sxs-lookup"><span data-stu-id="79e90-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="79e90-126">Fügen Sie ein **\<security>** -Element und das- `mode` Attribut auf fest `Message` .</span><span class="sxs-lookup"><span data-stu-id="79e90-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="79e90-127">**\<security>** Fügen Sie im-Element ein **\<message>** -Element hinzu, und legen Sie das- `clientCredentialType` Attribut auf fest `Certificate` .</span><span class="sxs-lookup"><span data-stu-id="79e90-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
