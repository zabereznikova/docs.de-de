---
title: 'Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung'
ms.date: 03/30/2017
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
ms.openlocfilehash: ee35f2a36ca08814423b5a3d0b1432bacd28c2e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973003"
---
# <a name="how-to-secure-messages-within-reliable-sessions"></a><span data-ttu-id="149f4-102">Vorgehensweise: Schützen von Nachrichten innerhalb einer zuverlässigen Sitzung</span><span class="sxs-lookup"><span data-stu-id="149f4-102">How to: Secure Messages within Reliable Sessions</span></span>

<span data-ttu-id="149f4-103">Dieses Thema enthält einen Überblick über die Schritte zum Aktivieren der Sicherheit auf Nachrichtenebene für den Nachrichtenaustausch innerhalb einer zuverlässigen Sitzung mithilfe einer der vom System bereitgestellten Bindungen, die eine solche Sitzung zwar unterstützen, standardmäßig aber keine Unterstützung dafür bieten.</span><span class="sxs-lookup"><span data-stu-id="149f4-103">This topic outlines the steps required to enable message-level security for messages exchanged within a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="149f4-104">Aktivieren Sie eine sichere, zuverlässige Sitzung, entweder verbindlich durch Verwenden von Code oder deklarativ in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="149f4-104">Enable a secure, reliable session either imperatively by using code or declaratively in the configuration file.</span></span> <span data-ttu-id="149f4-105">Dieses Verfahren verwendet die Konfigurationsdateien von Client und Dienst, um die sichere, zuverlässige Sitzung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="149f4-105">This procedure uses the client and service configuration files to enable the secure, reliable session.</span></span>

<span data-ttu-id="149f4-106">Dieses Verfahren besteht aus den folgenden drei Hauptaufgaben:</span><span class="sxs-lookup"><span data-stu-id="149f4-106">This procedure consists of the following three key tasks:</span></span>

1. <span data-ttu-id="149f4-107">Angeben, dass der Client und der Dienst Nachrichten in einer zuverlässigen Sitzung austauschen.</span><span class="sxs-lookup"><span data-stu-id="149f4-107">Specify that the client and service exchange messages within a reliable session.</span></span>

1. <span data-ttu-id="149f4-108">Anfordern der Sicherheit auf Nachrichtenebene innerhalb der zuverlässigen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="149f4-108">Require message-level security within the reliable session.</span></span>

1. <span data-ttu-id="149f4-109">Angeben des Clientanmeldeinformationstyps, den der Client verwenden muss, um sich selbst beim Server authentifizieren zu können.</span><span class="sxs-lookup"><span data-stu-id="149f4-109">Specify the client credential type that the client must use to be authenticated with the service.</span></span>

<span data-ttu-id="149f4-110">Es ist wichtig, in der ersten Aufgabe, die die Endpunkt-Konfigurationselement enthalten eine `bindingConfiguration` -Attribut, das auf die Bindungskonfiguration Namens (in diesem Beispiel) `MessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="149f4-110">It's important in the first task that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named (in this example) `MessageSecurity`.</span></span> <span data-ttu-id="149f4-111">Die [  **\<Bindung >** ](../../../../docs/framework/misc/binding.md) Konfigurationselement verweist dann auf diesen Namen, um zuverlässige Sitzungen zu aktivieren, indem Sie die Einstellung der `enabled` Attribut der [  **\<ReliableSession >** ](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) Element `true`.</span><span class="sxs-lookup"><span data-stu-id="149f4-111">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element then references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90)) element to `true`.</span></span> <span data-ttu-id="149f4-112">Sie können angeben, dass eine Zusicherung der Zustellung in der richtigen Reihenfolge innerhalb einer zuverlässigen Sitzung verfügbar ist, indem Sie das `ordered`-Attribut auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="149f4-112">You can require that the ordered delivery assurances are available within a reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="149f4-113">Die Quellkopie des Beispiels auf dem dieses Konfigurationsverfahren basiert, finden Sie unter den [zuverlässige WS-Sitzung](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="149f4-113">For the source copy of the example on which this configuration procedure is based, see the [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

<span data-ttu-id="149f4-114">Die wesentlichen Punkte der zweiten Aufgabe werden erreicht, indem Sie die Einstellung der `mode` Attribut der  **\<Sicherheit >** in enthaltenen Elementen der  **\<Bindung >** Element des dem Client und Dienst `Message`.</span><span class="sxs-lookup"><span data-stu-id="149f4-114">The essential items of the second task are accomplished by setting the `mode` attribute of the **\<security>** element contained in the **\<binding>** element of the client and service to `Message`.</span></span>

<span data-ttu-id="149f4-115">Die wesentlichen Punkte der dritten Aufgabe werden erreicht, indem Sie die Einstellung der `clientCredentialType` Attribut der  **\<Nachricht >** in enthaltenen Elementen der  **\<Sicherheit >** Element des dem Client und Dienst `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="149f4-115">The essential items of the third task are accomplished by setting the `clientCredentialType` attribute of the **\<message>** element contained in the **\<security>** element of the client and service to `Certificate`.</span></span>

> [!NOTE]
> <span data-ttu-id="149f4-116">Wenn Sie nachrichtensicherheit mit zuverlässigen Sitzungen verwenden, versucht das zuverlässiges Messaging einen nicht authentifizierten Client zu authentifizieren, bis ein Timeout auftritt, statt einer Ausnahme nach dem ersten Fehlschlag.</span><span class="sxs-lookup"><span data-stu-id="149f4-116">When using message security with reliable sessions, Reliable Messaging attempts to authenticate an unauthenticated client until a timeout occurs instead of throwing an exception upon first failure.</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="149f4-117">Konfigurieren Sie den Dienst mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung</span><span class="sxs-lookup"><span data-stu-id="149f4-117">Configure the service with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="149f4-118">Dieses Verfahren wird beschrieben, [Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="149f4-118">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="149f4-119">Konfigurieren Sie den Client mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung</span><span class="sxs-lookup"><span data-stu-id="149f4-119">Configure the client with a WSHttpBinding to use a reliable session</span></span>

<span data-ttu-id="149f4-120">Dieses Verfahren wird beschrieben, [Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="149f4-120">This procedure is described in [How to: Exchange Messages Within a Reliable Session](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md).</span></span>

### <a name="set-the-mode-and-clientcredentialtype-in-configuration"></a><span data-ttu-id="149f4-121">Festlegen Sie der Modus und den ClientCredentialType in der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="149f4-121">Set the mode and ClientCredentialType in configuration</span></span>

1. <span data-ttu-id="149f4-122">Fügen Sie ein entsprechendes Bindungselement, das [  **\<Bindungen >** ](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) Element der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="149f4-122">Add an appropriate binding element to the [**\<bindings>**](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="149f4-123">Im folgenden Beispiel wird eine [  **\<WsHttpBinding >** ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="149f4-123">The following example adds a [**\<wsHttpBinding>**](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

1. <span data-ttu-id="149f4-124">Hinzufügen einer  **\<Bindung >** Element, und legen dessen `name` -Attribut auf einen geeigneten Wert.</span><span class="sxs-lookup"><span data-stu-id="149f4-124">Add a **\<binding>** element and set its `name` attribute to an appropriate value.</span></span> <span data-ttu-id="149f4-125">Im Beispiel wird der Name `MessageSecurity`.</span><span class="sxs-lookup"><span data-stu-id="149f4-125">The example uses the name `MessageSecurity`.</span></span>

1. <span data-ttu-id="149f4-126">Hinzufügen einer  **\<Sicherheit >** Element, und legen die `mode` Attribut `Message`.</span><span class="sxs-lookup"><span data-stu-id="149f4-126">Add a **\<security>** element and set the `mode` attribute to `Message`.</span></span>

1. <span data-ttu-id="149f4-127">Innerhalb der  **\<Sicherheit >** -Element, Hinzufügen einer  **\<Nachricht >** Element, und legen die `clientCredentialType` Attribut `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="149f4-127">Within the **\<security>** element, add a **\<message>** element and set the `clientCredentialType` attribute to `Certificate`.</span></span>

```xml
<wsHttpBinding>
  <binding name="MessageSecurity">
    <security mode="Message">
      <message clientCredentialType="Certificate" />
    </security>
  </binding>
</wsHttpBinding>
```
