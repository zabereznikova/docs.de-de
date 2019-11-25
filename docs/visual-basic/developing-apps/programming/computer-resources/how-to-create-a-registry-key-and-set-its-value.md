---
title: 'Vorgehensweise: Erstellen von Registrierungsschlüsseln und Festlegen ihrer Werte'
ms.date: 07/20/2015
f1_keywords:
- RegistryKey.CreateSubKey
- RegistryKey.SetValue
helpviewer_keywords:
- registry keys [Visual Basic], creating
- registry [Visual Basic], adding values
- registry [Visual Basic], adding keys
- registry keys [Visual Basic], setting values
- examples [Visual Basic], registry
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
ms.openlocfilehash: 459c4b3f971009ee4b6b669c55bc058db0826595
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349202"
---
# <a name="how-to-create-a-registry-key-and-set-its-value-in-visual-basic"></a><span data-ttu-id="c7788-102">Vorgehensweise: Erstellen von Registrierungsschlüsseln und Festlegen von deren Werten in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7788-102">How to: Create a Registry Key and Set Its Value in Visual Basic</span></span>

<span data-ttu-id="c7788-103">Die `CreateSubKey`-Methode des `My.Computer.Registry`-Objekts kann verwendet werden, um einen Registrierungsschlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c7788-103">The `CreateSubKey` method of the `My.Computer.Registry` object can be used to create a registry key.</span></span>

## <a name="procedure"></a><span data-ttu-id="c7788-104">Prozedur</span><span class="sxs-lookup"><span data-stu-id="c7788-104">Procedure</span></span>

### <a name="to-create-a-registry-key"></a><span data-ttu-id="c7788-105">Erstellen eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="c7788-105">To create a registry key</span></span>

- <span data-ttu-id="c7788-106">Verwenden Sie die `CreateSubKey`-Methode, geben sie dabei an, unter welcher Struktur der Schlüssel platziert werden soll sowie den Namen des Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="c7788-106">Use the `CreateSubKey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="c7788-107">Der Parameter `Subkey` unterscheidet nicht zwischen Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="c7788-107">The parameter `Subkey` is not case-sensitive.</span></span> <span data-ttu-id="c7788-108">Dieses Beispiel erstellt den Registrierungsschlüssel `MyTestKey` unter HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="c7788-108">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>

    [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]

### <a name="to-create-a-registry-key-and-set-a-value-in-it"></a><span data-ttu-id="c7788-109">So erstellen Sie einen Registrierungsschlüssel und legen einen Wert darin fest</span><span class="sxs-lookup"><span data-stu-id="c7788-109">To create a registry key and set a value in it</span></span>

1. <span data-ttu-id="c7788-110">Verwenden Sie die `CreateSubkey`-Methode, geben sie dabei an, unter welcher Struktur der Schlüssel platziert werden soll sowie den Namen des Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="c7788-110">Use the `CreateSubkey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="c7788-111">Dieses Beispiel erstellt den Registrierungsschlüssel `MyTestKey` unter HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="c7788-111">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>

    [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]

2. <span data-ttu-id="c7788-112">Legen Sie den Wert mit der `SetValue`-Methode fest.</span><span class="sxs-lookup"><span data-stu-id="c7788-112">Set the value with the `SetValue` method.</span></span> <span data-ttu-id="c7788-113">Im folgenden Beispiel wird der Zeichenfolgenwert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c7788-113">This example sets the string value.</span></span> <span data-ttu-id="c7788-114">„MyTestKeyValue“ zu „Dies ist ein Testwert“.</span><span class="sxs-lookup"><span data-stu-id="c7788-114">"MyTestKeyValue" to "This is a test value".</span></span>

    [!code-vb[VbResourceTasks#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#14)]

## <a name="example"></a><span data-ttu-id="c7788-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7788-115">Example</span></span>

<span data-ttu-id="c7788-116">Dieses Beispiel erstellt den Registrierungsschlüssel `MyTestKey` unter HKEY_CURRENT_USER und legt den Zeichenfolgenwert `MyTestKeyValue` auf `This is a test value` fest.</span><span class="sxs-lookup"><span data-stu-id="c7788-116">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER and then sets the string value `MyTestKeyValue` to `This is a test value`.</span></span>

[!code-vb[VbResourceTasks#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#15)]

## <a name="robust-programming"></a><span data-ttu-id="c7788-117">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="c7788-117">Robust Programming</span></span>

<span data-ttu-id="c7788-118">Untersuchen Sie die Registrierungsstruktur, um eine adäquate Position für den Schlüssel zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c7788-118">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="c7788-119">Sie können beispielsweise den Schlüssel HKEY_CURRENT_USER\Software des aktuellen Benutzers öffnen und einen Schlüssel mit dem Namen Ihres Unternehmens erstellen.</span><span class="sxs-lookup"><span data-stu-id="c7788-119">For example, you may want to open the HKEY_CURRENT_USER\Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="c7788-120">Anschließend fügen Sie die Registrierungswerte dem Schlüssel für das Unternehmen hinzu.</span><span class="sxs-lookup"><span data-stu-id="c7788-120">Then add the registry values to your company's key.</span></span>

<span data-ttu-id="c7788-121">Wenn Sie die Registrierung von einer Webanwendung lesen, hängt der aktuelle Benutzer von der Authentifizierung und dem Identitätswechsel ab, die in der Webanwendung implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="c7788-121">When reading the registry from a Web application, the current user depends on the authentication and impersonation implemented in the Web application.</span></span>

<span data-ttu-id="c7788-122">Es ist sicherer, die Daten in den Benutzerordner (<xref:Microsoft.Win32.Registry.CurrentUser>) anstatt auf den lokalen Computer (<xref:Microsoft.Win32.Registry.LocalMachine>) zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="c7788-122">It is more secure to write data to the user folder (<xref:Microsoft.Win32.Registry.CurrentUser>) rather than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span>

<span data-ttu-id="c7788-123">Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c7788-123">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="c7788-124">Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="c7788-124">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="c7788-125">Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c7788-125">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="c7788-126">Um dies zu verhindern, verwenden Sie die <xref:Microsoft.Win32.RegistryKey.GetValue%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="c7788-126">To prevent this, use the <xref:Microsoft.Win32.RegistryKey.GetValue%2A> method.</span></span> <span data-ttu-id="c7788-127">Die Methode gibt `Nothing` zurück, wenn der Schlüssel noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c7788-127">It returns `Nothing` if the key does not already exist.</span></span>

<span data-ttu-id="c7788-128">Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als Klartext zu speichern. Dies gilt auch, wenn der Registrierungsschlüssel durch Zugriffssteuerungslisten (ACLs) geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="c7788-128">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (Access Control Lists).</span></span>

<span data-ttu-id="c7788-129">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="c7788-129">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="c7788-130">Der Name des Schlüssels lautet `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="c7788-130">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="c7788-131">Der Benutzer ist nicht zum Erstellen von Registrierungsschlüsseln berechtigt (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="c7788-131">The user does not have permissions to create registry keys (<xref:System.Security.SecurityException>).</span></span>

- <span data-ttu-id="c7788-132">Der Name des Schlüssels überschreitet das Limit von 255 Zeichen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="c7788-132">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="c7788-133">Der Schlüssel ist geschlossen (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="c7788-133">The key is closed (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="c7788-134">Der Registrierungsschlüssel ist schreibgeschützt (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="c7788-134">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="c7788-135">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c7788-135">.NET Framework Security</span></span>

<span data-ttu-id="c7788-136">Die Assembly benötigt zum Ausführen dieses Prozesses eine von der <xref:System.Security.Permissions.RegistryPermission>-Klasse gewährte Berechtigungsebene.</span><span class="sxs-lookup"><span data-stu-id="c7788-136">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="c7788-137">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="c7788-137">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="c7788-138">Ebenso muss der Benutzer die richtigen Zugriffssteuerungslisten zum Erstellen von oder Schreiben auf Einstellungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="c7788-138">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="c7788-139">Beispielsweise besitzt eine lokale Anwendung, die die Sicherheitsberechtigung für den Codezugriff besitzt, möglicherweise keine Betriebssystemberechtigung.</span><span class="sxs-lookup"><span data-stu-id="c7788-139">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="c7788-140">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="c7788-140">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c7788-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7788-141">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A>
- <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>
- [<span data-ttu-id="c7788-142">Lesen aus der und Schreiben in die Registrierung</span><span class="sxs-lookup"><span data-stu-id="c7788-142">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
- [<span data-ttu-id="c7788-143">Grundlagen der Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="c7788-143">Code Access Security Basics</span></span>](../../../../framework/misc/code-access-security-basics.md)
