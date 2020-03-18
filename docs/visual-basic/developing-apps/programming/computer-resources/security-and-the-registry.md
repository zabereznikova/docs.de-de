---
title: Sicherheit und die Registrierung
ms.date: 07/20/2015
helpviewer_keywords:
- security [Visual Basic], registry
- registry [Visual Basic], security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
ms.openlocfilehash: 454180207d6432e80d87941d1f329f2a4ea7a801
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345483"
---
# <a name="security-and-the-registry-visual-basic"></a><span data-ttu-id="eec49-102">Sicherheit und die Registrierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eec49-102">Security and the Registry (Visual Basic)</span></span>

<span data-ttu-id="eec49-103">Diese Seite beschreibt die Sicherheitsauswirkungen bei der Speicherung von Daten in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="eec49-103">This page discusses the security implications of storing data in the registry.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="eec49-104">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="eec49-104">Permissions</span></span>  

 <span data-ttu-id="eec49-105">Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als Klartext zu speichern. Dies gilt auch, wenn der Registrierungsschlüssel durch Zugriffssteuerungslisten (ACLs) geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="eec49-105">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (access control lists).</span></span>  
  
 <span data-ttu-id="eec49-106">Das Arbeiten mit der Registrierung schränkt möglicherweise die Sicherheit ein, da nicht ordnungsgemäßer Zugriff auf Systemressourcen oder geschützte Informationen zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="eec49-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span> <span data-ttu-id="eec49-107">Um diese Eigenschaften verwenden zu können, benötigen Sie Lese- und Schreibberechtigungen aus der Enumeration <xref:System.Security.Permissions.RegistryPermissionAccess>, die den Zugriff auf Registrierungsvariablen steuert.</span><span class="sxs-lookup"><span data-stu-id="eec49-107">To use these properties, you must have read and write permissions from the <xref:System.Security.Permissions.RegistryPermissionAccess> enumeration, which controls access to registry variables.</span></span> <span data-ttu-id="eec49-108">Jeder Code, der mit voller Vertrauenswürdigkeit ausgeführt wird (gemäß der Standardsicherheitsrichtlinie ist dies jeder Code, der auf der lokalen Festplatte des Benutzers installiert ist) verfügt über die erforderlichen Berechtigungen zum Zugriff auf die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="eec49-108">Any code running with full trust (under the default security policy, this is any code installed on the user's local hard disk) has the necessary permissions to access the registry.</span></span> <span data-ttu-id="eec49-109">Weitere Informationen finden Sie in der <xref:System.Security.Permissions.RegistryPermission>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="eec49-109">For more information, see <xref:System.Security.Permissions.RegistryPermission> class.</span></span>  
  
 <span data-ttu-id="eec49-110">Registrierungsvariablen sollten nicht an Speicherorten gespeichert werden, in denen Code ohne <xref:System.Security.Permissions.RegistryPermission> darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="eec49-110">Registry variables should not be stored in memory locations where code without <xref:System.Security.Permissions.RegistryPermission> can access them.</span></span> <span data-ttu-id="eec49-111">Gewähren Sie auf ähnliche Weise die zur Erledigung der Aufgabe erforderlichen Mindestberechtigungen, wenn Sie Berechtigungen erteilen.</span><span class="sxs-lookup"><span data-stu-id="eec49-111">Similarly, when granting permissions, grant the minimum privileges necessary to get the job done.</span></span>  
  
 <span data-ttu-id="eec49-112">Zugriffswerte für Registrierungsberechtigungen werden von der Enumeration <xref:System.Security.Permissions.RegistryPermissionAccess> definiert.</span><span class="sxs-lookup"><span data-stu-id="eec49-112">Registry permission access values are defined by the <xref:System.Security.Permissions.RegistryPermissionAccess> enumeration.</span></span> <span data-ttu-id="eec49-113">In der folgenden Tabelle werden die Member aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="eec49-113">The following table details its members.</span></span>  
  
|<span data-ttu-id="eec49-114">Wert</span><span class="sxs-lookup"><span data-stu-id="eec49-114">Value</span></span>|<span data-ttu-id="eec49-115">Zugriff auf Registrierungsvariablen</span><span class="sxs-lookup"><span data-stu-id="eec49-115">Access to Registry Variables</span></span>|  
|-----------|----------------------------------|  
|`AllAccess`|<span data-ttu-id="eec49-116">Erstellen, Lesen und Schreiben</span><span class="sxs-lookup"><span data-stu-id="eec49-116">Create, read, and write</span></span>|  
|`Create`|<span data-ttu-id="eec49-117">Erstellen</span><span class="sxs-lookup"><span data-stu-id="eec49-117">Create</span></span>|  
|`NoAccess`|<span data-ttu-id="eec49-118">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="eec49-118">No access</span></span>|  
|`Read`|<span data-ttu-id="eec49-119">Lesen</span><span class="sxs-lookup"><span data-stu-id="eec49-119">Read</span></span>|  
|`Write`|<span data-ttu-id="eec49-120">Write</span><span class="sxs-lookup"><span data-stu-id="eec49-120">Write</span></span>|  
  
## <a name="checking-values-in-registry-keys"></a><span data-ttu-id="eec49-121">Überprüfen von Werten in Registrierungsschlüsseln</span><span class="sxs-lookup"><span data-stu-id="eec49-121">Checking Values in Registry Keys</span></span>  

 <span data-ttu-id="eec49-122">Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="eec49-122">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="eec49-123">Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="eec49-123">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="eec49-124">Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="eec49-124">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="eec49-125">Um dies zu verhindern, verwenden Sie die `GetValue`-Methode.</span><span class="sxs-lookup"><span data-stu-id="eec49-125">To prevent this, use the `GetValue` method.</span></span> <span data-ttu-id="eec49-126">Die Methode gibt `Nothing` zurück, wenn der Schlüssel noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="eec49-126">It returns `Nothing` if the key does not already exist.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="eec49-127">Wenn Sie die Registrierung von einer Webanwendung lesen, hängt die Identität aktueller Benutzer von der Authentifizierung und dem Identitätswechsel ab, die in der Webanwendung implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="eec49-127">When reading the registry from a Web application, the identity of current user depends on the authentication and impersonation implemented in the Web application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec49-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eec49-128">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [<span data-ttu-id="eec49-129">Lesen aus der und Schreiben in die Registrierung</span><span class="sxs-lookup"><span data-stu-id="eec49-129">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
