---
title: "Gewusst wie: Löschen von Registrierungsschlüsseln in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.DeleteSetting
helpviewer_keywords:
- GetSetting function [Visual Basic]
- registry [Visual Basic], deleting values
- GetAllSettings function
- registry keys [Visual Basic], deleting
- registry [Visual Basic], deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0cb98c02531bac133b9dc37a92f75d5c0418dc7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a><span data-ttu-id="d2136-102">Gewusst wie: Löschen von Registrierungsschlüsseln in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d2136-102">How to: Delete a Registry Key in Visual Basic</span></span>
<span data-ttu-id="d2136-103">Die Methoden <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> und <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> können zum Löschen von Registrierungsschlüsseln verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d2136-103">The <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> and <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> methods can be used to delete registry keys.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="d2136-104">Prozedur</span><span class="sxs-lookup"><span data-stu-id="d2136-104">Procedure</span></span>  
  
#### <a name="to-delete-a-registry-key"></a><span data-ttu-id="d2136-105">Löschen von Registrierungsschlüsseln</span><span class="sxs-lookup"><span data-stu-id="d2136-105">To delete a registry key</span></span>  
  
-   <span data-ttu-id="d2136-106">Verwenden Sie die `DeleteSubKey`-Methode zum Löschen von Registrierungsschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d2136-106">Use the `DeleteSubKey` method to delete a registry key.</span></span> <span data-ttu-id="d2136-107">In diesem Beispiel wird der Schlüssel „Software/TestApp“ aus der Struktur „CurrentUser“ gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d2136-107">This example deletes the key Software/TestApp in the CurrentUser hive.</span></span> <span data-ttu-id="d2136-108">Dies können Sie im Code in die entsprechende Zeichenfolge ändern, oder Sie können es von vom Benutzer zur Verfügung gestellten Informationen abhängig machen.</span><span class="sxs-lookup"><span data-stu-id="d2136-108">You can change this in the code to the appropriate string, or have it rely on user-supplied information.</span></span>  
  
     [!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="d2136-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="d2136-109">Robust Programming</span></span>  
 <span data-ttu-id="d2136-110">Die `DeleteSubKey`-Methode gibt eine leere Zeichenfolge zurück, wenn das Schlüssel-Wert-Paar nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d2136-110">The `DeleteSubKey` method returns an empty string if the key/value pair does not exist.</span></span>  
  
 <span data-ttu-id="d2136-111">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="d2136-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="d2136-112">Der Name des Schlüssels lautet `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="d2136-112">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="d2136-113">Der Benutzer ist nicht zum Löschen von Registrierungsschlüsseln berechtigt (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="d2136-113">The user does not have permissions to delete registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="d2136-114">Der Name des Schlüssels überschreitet das Limit von 255 Zeichen (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="d2136-114">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="d2136-115">Der Registrierungsschlüssel ist schreibgeschützt (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="d2136-115">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d2136-116">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d2136-116">.NET Framework Security</span></span>  
 <span data-ttu-id="d2136-117">Registrierungsaufrufe schlagen fehl, wenn die notwendigen Laufzeitberechtigungen fehlen (<xref:System.Security.Permissions.RegistryPermission>), oder wenn der Benutzer nicht über den korrekten Zugriff (wie von den ACLs angegeben) für das Erstellen von und Schreiben in Einstellungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="d2136-117">Registry calls fail if either sufficient run-time permissions are not granted (<xref:System.Security.Permissions.RegistryPermission>) or if the user does not have the correct access (as determined by the ACLs) for creating or writing to settings.</span></span> <span data-ttu-id="d2136-118">Beispielsweise besitzt eine lokale Anwendung, die die Sicherheitsberechtigung für den Codezugriff besitzt, möglicherweise keine Betriebssystemberechtigung.</span><span class="sxs-lookup"><span data-stu-id="d2136-118">For example, a local application that has the code access security permission might not have operating system permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2136-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2136-119">See Also</span></span>  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>  
 <xref:Microsoft.Win32.RegistryKey>  
 [<span data-ttu-id="d2136-120">Sicherheit und die Registrierung</span><span class="sxs-lookup"><span data-stu-id="d2136-120">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 [<span data-ttu-id="d2136-121">Lesen aus der und Schreiben in die Registrierung</span><span class="sxs-lookup"><span data-stu-id="d2136-121">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
