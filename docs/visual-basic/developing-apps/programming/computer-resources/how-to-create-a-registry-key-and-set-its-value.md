---
title: "Gewusst wie: Erstellen von Registrierungsschlüsseln und Festlegen von deren Werten in Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- RegistryKey.CreateSubKey
- RegistryKey.SetValue
dev_langs:
- VB
helpviewer_keywords:
- registry keys, creating
- registry, adding values
- registry, adding keys
- registry keys, setting values
- examples [Visual Basic], registry
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 106a98a1b15c37eb2cac05e1a681bf7dfed3543d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-registry-key-and-set-its-value-in-visual-basic"></a><span data-ttu-id="8227a-102">Gewusst wie: Erstellen von Registrierungsschlüsseln und Festlegen von deren Werten in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8227a-102">How to: Create a Registry Key and Set Its Value in Visual Basic</span></span>
<span data-ttu-id="8227a-103">Die `CreateSubKey`-Methode des `My.Computer.Registry`-Objekts kann verwendet werden, um einen Registrierungsschlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8227a-103">The `CreateSubKey` method of the `My.Computer.Registry` object can be used to create a registry key.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="8227a-104">Prozedur</span><span class="sxs-lookup"><span data-stu-id="8227a-104">Procedure</span></span>  
  
#### <a name="to-create-a-registry-key"></a><span data-ttu-id="8227a-105">Erstellen eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="8227a-105">To create a registry key</span></span>  
  
-   <span data-ttu-id="8227a-106">Verwenden Sie die `CreateSubKey`-Methode, geben sie dabei an, unter welcher Struktur der Schlüssel platziert werden soll sowie den Namen des Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="8227a-106">Use the `CreateSubKey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="8227a-107">Der Parameter `Subkey` unterscheidet nicht zwischen Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="8227a-107">The parameter `Subkey` is not case-sensitive.</span></span> <span data-ttu-id="8227a-108">Dieses Beispiel erstellt den Registrierungsschlüssel `MyTestKey` unter HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="8227a-108">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>  
  
     <span data-ttu-id="8227a-109">[!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8227a-109">[!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]</span></span>  
  
#### <a name="to-create-a-registry-key-and-set-a-value-in-it"></a><span data-ttu-id="8227a-110">So erstellen Sie einen Registrierungsschlüssel und legen einen Wert darin fest</span><span class="sxs-lookup"><span data-stu-id="8227a-110">To create a registry key and set a value in it</span></span>  
  
1.  <span data-ttu-id="8227a-111">Verwenden Sie die `CreateSubkey`-Methode, geben sie dabei an, unter welcher Struktur der Schlüssel platziert werden soll sowie den Namen des Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="8227a-111">Use the `CreateSubkey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="8227a-112">Dieses Beispiel erstellt den Registrierungsschlüssel `MyTestKey` unter HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="8227a-112">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>  
  
     <span data-ttu-id="8227a-113">[!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8227a-113">[!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]</span></span>  
  
2.  <span data-ttu-id="8227a-114">Legen Sie den Wert mit der `SetValue`-Methode fest.</span><span class="sxs-lookup"><span data-stu-id="8227a-114">Set the value with the `SetValue` method.</span></span> <span data-ttu-id="8227a-115">Im folgenden Beispiel wird der Zeichenfolgenwert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8227a-115">This example sets the string value.</span></span> <span data-ttu-id="8227a-116">„MyTestKeyValue“ zu „Dies ist ein Testwert“.</span><span class="sxs-lookup"><span data-stu-id="8227a-116">"MyTestKeyValue" to "This is a test value".</span></span>  
  
     <span data-ttu-id="8227a-117">[!code-vb[VbResourceTasks#14](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8227a-117">[!code-vb[VbResourceTasks#14](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8227a-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8227a-118">Example</span></span>  
 <span data-ttu-id="8227a-119">Dieses Beispiel erstellt den Registrierungsschlüssel `MyTestKey` unter HKEY_CURRENT_USER und legt den Zeichenfolgenwert `MyTestKeyValue` auf `This is a test value` fest.</span><span class="sxs-lookup"><span data-stu-id="8227a-119">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER and then sets the string value `MyTestKeyValue` to `This is a test value`.</span></span>  
  
 <span data-ttu-id="8227a-120">[!code-vb[VbResourceTasks#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8227a-120">[!code-vb[VbResourceTasks#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_3.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8227a-121">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="8227a-121">Robust Programming</span></span>  
 <span data-ttu-id="8227a-122">Untersuchen Sie die Registrierungsstruktur, um eine adäquate Position für den Schlüssel zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="8227a-122">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="8227a-123">Sie können beispielsweise den Schlüssel HKEY_CURRENT_USER\Software des aktuellen Benutzers öffnen und einen Schlüssel mit dem Namen Ihres Unternehmens erstellen.</span><span class="sxs-lookup"><span data-stu-id="8227a-123">For example, you may want to open the HKEY_CURRENT_USER\Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="8227a-124">Anschließend fügen Sie die Registrierungswerte dem Schlüssel für das Unternehmen hinzu.</span><span class="sxs-lookup"><span data-stu-id="8227a-124">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="8227a-125">Wenn Sie die Registrierung von einer Webanwendung lesen, hängt der aktuelle Benutzer von der Authentifizierung und dem Identitätswechsel ab, die in der Webanwendung implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="8227a-125">When reading the registry from a Web application, the current user depends on the authentication and impersonation implemented in the Web application.</span></span>  
  
 <span data-ttu-id="8227a-126">Es ist sicherer, die Daten in den Benutzerordner (<xref:Microsoft.Win32.Registry.CurrentUser>) anstatt auf den lokalen Computer (<xref:Microsoft.Win32.Registry.LocalMachine>) zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="8227a-126">It is more secure to write data to the user folder (<xref:Microsoft.Win32.Registry.CurrentUser>) rather than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span>  
  
 <span data-ttu-id="8227a-127">Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8227a-127">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="8227a-128">Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="8227a-128">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="8227a-129">Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8227a-129">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="8227a-130">Um dies zu verhindern, verwenden Sie die <xref:Microsoft.Win32.RegistryKey.GetValue%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="8227a-130">To prevent this, use the <xref:Microsoft.Win32.RegistryKey.GetValue%2A> method.</span></span> <span data-ttu-id="8227a-131">Die Methode gibt `Nothing` zurück, wenn der Schlüssel noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8227a-131">It returns `Nothing` if the key does not already exist.</span></span>  
  
 <span data-ttu-id="8227a-132">Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als Klartext zu speichern. Dies gilt auch, wenn der Registrierungsschlüssel durch Zugriffssteuerungslisten (ACLs) geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="8227a-132">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (Access Control Lists).</span></span>  
  
 <span data-ttu-id="8227a-133">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="8227a-133">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="8227a-134">Der Name des Schlüssels lautet `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="8227a-134">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="8227a-135">Der Benutzer ist nicht zum Erstellen von Registrierungsschlüsseln berechtigt (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="8227a-135">The user does not have permissions to create registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="8227a-136">Der Name des Schlüssels überschreitet das Limit von 255 Zeichen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="8227a-136">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="8227a-137">Der Schlüssel ist geschlossen (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="8227a-137">The key is closed (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="8227a-138">Der Registrierungsschlüssel ist schreibgeschützt (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="8227a-138">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8227a-139">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8227a-139">.NET Framework Security</span></span>  
 <span data-ttu-id="8227a-140">Die Assembly benötigt zum Ausführen dieses Prozesses eine von der <xref:System.Security.Permissions.RegistryPermission>-Klasse gewährte Berechtigungsebene.</span><span class="sxs-lookup"><span data-stu-id="8227a-140">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="8227a-141">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="8227a-141">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="8227a-142">Ebenso muss der Benutzer die richtigen Zugriffssteuerungslisten zum Erstellen von oder Schreiben auf Einstellungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="8227a-142">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="8227a-143">Beispielsweise besitzt eine lokale Anwendung, die die Sicherheitsberechtigung für den Codezugriff besitzt, möglicherweise keine Betriebssystemberechtigung.</span><span class="sxs-lookup"><span data-stu-id="8227a-143">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="8227a-144">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](https://msdn.microsoft.com/library/33tceax8).</span><span class="sxs-lookup"><span data-stu-id="8227a-144">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8227a-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8227a-145">See Also</span></span>  
 <span data-ttu-id="8227a-146"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span><span class="sxs-lookup"><span data-stu-id="8227a-146"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span></span>   
 <span data-ttu-id="8227a-147"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A></span><span class="sxs-lookup"><span data-stu-id="8227a-147"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A></span></span>   
 <span data-ttu-id="8227a-148"><xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A></span><span class="sxs-lookup"><span data-stu-id="8227a-148"><xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A></span></span>   
 <span data-ttu-id="8227a-149">[Lesen aus der und Schreiben in die Registrierung](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="8227a-149">[Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span></span>  
 [<span data-ttu-id="8227a-150">Grundlagen der Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="8227a-150">Code Access Security Basics</span></span>](https://msdn.microsoft.com/library/33tceax8)

