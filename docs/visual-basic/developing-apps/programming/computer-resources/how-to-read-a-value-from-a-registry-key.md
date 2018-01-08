---
title: "Gewusst wie: Lesen eines Werts aus einem Registrierungsschlüssel in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- registry keys [Visual Basic], determining if a value exists in
- My.Computer.Registry object, examples
- registry [Visual Basic], determining if values exist
- registry keys [Visual Basic], reading from
- registry [Visual Basic], reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4aa939d7b2d89bd878705ac67f2b6f37838f6ea2
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a><span data-ttu-id="f90c9-102">Gewusst wie: Lesen eines Werts aus einem Registrierungsschlüssel in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f90c9-102">How to: Read a Value from a Registry Key in Visual Basic</span></span>
<span data-ttu-id="f90c9-103">Die `GetValue`-Methode des `My.Computer.Registry`-Objekts kann verwendet werden, um Werte in der Windows-Registrierung zu lesen.</span><span class="sxs-lookup"><span data-stu-id="f90c9-103">The `GetValue` method of the `My.Computer.Registry` object can be used to read values in the Windows registry.</span></span>  
  
 <span data-ttu-id="f90c9-104">Wenn der Schlüssel („Software\MyApp“ im folgenden Beispiel) nicht vorhanden ist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f90c9-104">If the key, "Software\MyApp" in the following example, does not exist, an exception is thrown.</span></span> <span data-ttu-id="f90c9-105">Wenn der `ValueName` („Name“ im folgenden Beispiel) nicht vorhanden ist, wird `Nothing` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f90c9-105">If the `ValueName`,  "Name" in the following example, does not exist, `Nothing` is returned.</span></span>  
  
 <span data-ttu-id="f90c9-106">Die `GetValue`-Methode kann auch verwendet werden, um zu bestimmen, ob ein bestimmter Wert in einem bestimmten Registrierungsschlüssel vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f90c9-106">The `GetValue` method can also be used to determine whether a given value exists in a specific registry key.</span></span>  
  
 <span data-ttu-id="f90c9-107">Wenn Code aus einer Webanwendung die Registrierung liest, wird der aktuelle Benutzer durch die Authentifizierung und den Identitätswechsel bestimmt, die in der Webanwendung implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="f90c9-107">When code reads the registry from a Web application, the current user is determined by the authentication and impersonation that is implemented in the Web application.</span></span>  
  
### <a name="to-read-a-value-from-a-registry-key"></a><span data-ttu-id="f90c9-108">Lesen eines Werts aus einem Registrierungsschlüssel</span><span class="sxs-lookup"><span data-stu-id="f90c9-108">To read a value from a registry key</span></span>  
  
-   <span data-ttu-id="f90c9-109">Verwenden Sie die `GetValue`-Methode, und geben Sie den Pfad und Namen an, um einen Wert aus dem Registrierungsschlüssel zu lesen.</span><span class="sxs-lookup"><span data-stu-id="f90c9-109">Use the `GetValue` method, specifying the path and name) to read a value from registry key.</span></span> <span data-ttu-id="f90c9-110">Das folgende Beispiel liest den Wert `Name` aus `HKEY_CURRENT_USER\Software\MyApp` und zeigt ihn in einem Nachrichtenfeld an.</span><span class="sxs-lookup"><span data-stu-id="f90c9-110">The following example reads the value `Name` from `HKEY_CURRENT_USER\Software\MyApp` and displays it in a message box.</span></span>  
  
     [!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]  
  
 <span data-ttu-id="f90c9-111">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f90c9-111">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="f90c9-112">Er befindet sich in der Codeausschnittauswahl unter **Windows Betriebssystem > Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="f90c9-112">In the code snippet picker, it is located in **Windows Operating System > Registry**.</span></span> <span data-ttu-id="f90c9-113">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="f90c9-113">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a><span data-ttu-id="f90c9-114">Bestimmen, ob ein Wert in einem Registrierungsschlüssel vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="f90c9-114">To determine whether a value exists in a registry key</span></span>  
  
-   <span data-ttu-id="f90c9-115">Verwenden Sie die `GetValue`-Methode, um den Wert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f90c9-115">Use the `GetValue` method to retrieve the value.</span></span> <span data-ttu-id="f90c9-116">Der folgende Code überprüft, ob der Wert vorhanden ist, und gibt eine Meldung zurück, wenn dies nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="f90c9-116">The following code checks whether the value exists and returns a message if it does not.</span></span>  
  
     [!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="f90c9-117">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="f90c9-117">Robust Programming</span></span>  
 <span data-ttu-id="f90c9-118">Die Registrierung enthält Schlüssel der obersten Ebene oder Stammschlüssel, die zum Speichern von Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f90c9-118">The registry holds top-level, or root, keys that are used to store data.</span></span> <span data-ttu-id="f90c9-119">Beispielsweise wird der HKEY_LOCAL_MACHINE-Stammschlüssel zum Speichern von Einstellungen auf Computerebene genutzt, die von allen Benutzern verwendet werden, während HKEY_CURRENT_USER zum Speichern von Daten genutzt wird, die spezifisch für einen einzelnen Benutzer sind.</span><span class="sxs-lookup"><span data-stu-id="f90c9-119">For instance, the HKEY_LOCAL_MACHINE root key is used for storing machine-level settings used by all users, while HKEY_CURRENT_USER is used for storing data specific to an individual user.</span></span>  
  
 <span data-ttu-id="f90c9-120">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="f90c9-120">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="f90c9-121">Der Name des Schlüssels lautet `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="f90c9-121">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="f90c9-122">Der Benutzer ist zum Lesen von Registrierungsschlüsseln nicht berechtigt (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="f90c9-122">The user does not have permissions to read from registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="f90c9-123">Der Name des Schlüssels überschreitet das Limit von 255 Zeichen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="f90c9-123">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f90c9-124">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f90c9-124">.NET Framework Security</span></span>  
 <span data-ttu-id="f90c9-125">Die Assembly benötigt zum Ausführen dieses Prozesses eine von der <xref:System.Security.Permissions.RegistryPermission>-Klasse gewährte Berechtigungsebene.</span><span class="sxs-lookup"><span data-stu-id="f90c9-125">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="f90c9-126">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="f90c9-126">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="f90c9-127">Ebenso muss der Benutzer die richtigen Zugriffssteuerungslisten zum Erstellen von oder Schreiben auf Einstellungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="f90c9-127">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="f90c9-128">Beispielsweise besitzt eine lokale Anwendung, die die Sicherheitsberechtigung für den Codezugriff besitzt, möglicherweise keine Betriebssystemberechtigung.</span><span class="sxs-lookup"><span data-stu-id="f90c9-128">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="f90c9-129">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="f90c9-129">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f90c9-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f90c9-130">See Also</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 <xref:Microsoft.Win32.RegistryHive>  
 [<span data-ttu-id="f90c9-131">Lesen aus der und Schreiben in die Registrierung</span><span class="sxs-lookup"><span data-stu-id="f90c9-131">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
