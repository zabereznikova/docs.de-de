---
title: Sicherheit und die Registrierung
ms.date: 07/20/2015
helpviewer_keywords:
- security [Visual Basic], registry
- registry [Visual Basic], security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
ms.openlocfilehash: 454180207d6432e80d87941d1f329f2a4ea7a801
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345483"
---
# <a name="security-and-the-registry-visual-basic"></a><span data-ttu-id="73ff8-102">Sicherheit und die Registrierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73ff8-102">Security and the Registry (Visual Basic)</span></span>

<span data-ttu-id="73ff8-103">Diese Seite beschreibt die Sicherheitsauswirkungen bei der Speicherung von Daten in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="73ff8-103">This page discusses the security implications of storing data in the registry.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="73ff8-104">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="73ff8-104">Permissions</span></span>  

 <span data-ttu-id="73ff8-105">Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als Klartext zu speichern. Dies gilt auch, wenn der Registrierungsschlüssel durch Zugriffssteuerungslisten (ACLs) geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="73ff8-105">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (access control lists).</span></span>  
  
 <span data-ttu-id="73ff8-106">Das Arbeiten mit der Registrierung schränkt möglicherweise die Sicherheit ein, da nicht ordnungsgemäßer Zugriff auf Systemressourcen oder geschützte Informationen zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="73ff8-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span> <span data-ttu-id="73ff8-107">Um diese Eigenschaften verwenden zu können, benötigen Sie Lese- und Schreibberechtigungen aus der Enumeration <xref:System.Security.Permissions.RegistryPermissionAccess>, die den Zugriff auf Registrierungsvariablen steuert.</span><span class="sxs-lookup"><span data-stu-id="73ff8-107">To use these properties, you must have read and write permissions from the <xref:System.Security.Permissions.RegistryPermissionAccess> enumeration, which controls access to registry variables.</span></span> <span data-ttu-id="73ff8-108">Jeder Code, der mit voller Vertrauenswürdigkeit ausgeführt wird (gemäß der Standardsicherheitsrichtlinie ist dies jeder Code, der auf der lokalen Festplatte des Benutzers installiert ist) verfügt über die erforderlichen Berechtigungen zum Zugriff auf die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="73ff8-108">Any code running with full trust (under the default security policy, this is any code installed on the user's local hard disk) has the necessary permissions to access the registry.</span></span> <span data-ttu-id="73ff8-109">Weitere Informationen finden Sie in der <xref:System.Security.Permissions.RegistryPermission>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="73ff8-109">For more information, see <xref:System.Security.Permissions.RegistryPermission> class.</span></span>  
  
 <span data-ttu-id="73ff8-110">Registrierungsvariablen sollten nicht an Speicherorten gespeichert werden, in denen Code ohne <xref:System.Security.Permissions.RegistryPermission> darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="73ff8-110">Registry variables should not be stored in memory locations where code without <xref:System.Security.Permissions.RegistryPermission> can access them.</span></span> <span data-ttu-id="73ff8-111">Gewähren Sie auf ähnliche Weise die zur Erledigung der Aufgabe erforderlichen Mindestberechtigungen, wenn Sie Berechtigungen erteilen.</span><span class="sxs-lookup"><span data-stu-id="73ff8-111">Similarly, when granting permissions, grant the minimum privileges necessary to get the job done.</span></span>  
  
 <span data-ttu-id="73ff8-112">Zugriffswerte für Registrierungsberechtigungen werden von der Enumeration <xref:System.Security.Permissions.RegistryPermissionAccess> definiert.</span><span class="sxs-lookup"><span data-stu-id="73ff8-112">Registry permission access values are defined by the <xref:System.Security.Permissions.RegistryPermissionAccess> enumeration.</span></span> <span data-ttu-id="73ff8-113">In der folgenden Tabelle werden die Member aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="73ff8-113">The following table details its members.</span></span>  
  
|<span data-ttu-id="73ff8-114">Wert</span><span class="sxs-lookup"><span data-stu-id="73ff8-114">Value</span></span>|<span data-ttu-id="73ff8-115">Zugriff auf Registrierungsvariablen</span><span class="sxs-lookup"><span data-stu-id="73ff8-115">Access to Registry Variables</span></span>|  
|-----------|----------------------------------|  
|`AllAccess`|<span data-ttu-id="73ff8-116">Erstellen, Lesen und Schreiben</span><span class="sxs-lookup"><span data-stu-id="73ff8-116">Create, read, and write</span></span>|  
|`Create`|<span data-ttu-id="73ff8-117">Erstellen</span><span class="sxs-lookup"><span data-stu-id="73ff8-117">Create</span></span>|  
|`NoAccess`|<span data-ttu-id="73ff8-118">Kein Zugriff</span><span class="sxs-lookup"><span data-stu-id="73ff8-118">No access</span></span>|  
|`Read`|<span data-ttu-id="73ff8-119">Lesen</span><span class="sxs-lookup"><span data-stu-id="73ff8-119">Read</span></span>|  
|`Write`|<span data-ttu-id="73ff8-120">Write</span><span class="sxs-lookup"><span data-stu-id="73ff8-120">Write</span></span>|  
  
## <a name="checking-values-in-registry-keys"></a><span data-ttu-id="73ff8-121">Überprüfen von Werten in Registrierungsschlüsseln</span><span class="sxs-lookup"><span data-stu-id="73ff8-121">Checking Values in Registry Keys</span></span>  

 <span data-ttu-id="73ff8-122">Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="73ff8-122">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="73ff8-123">Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="73ff8-123">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="73ff8-124">Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="73ff8-124">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="73ff8-125">Um dies zu verhindern, verwenden Sie die `GetValue`-Methode.</span><span class="sxs-lookup"><span data-stu-id="73ff8-125">To prevent this, use the `GetValue` method.</span></span> <span data-ttu-id="73ff8-126">Die Methode gibt `Nothing` zurück, wenn der Schlüssel noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="73ff8-126">It returns `Nothing` if the key does not already exist.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="73ff8-127">Wenn Sie die Registrierung von einer Webanwendung lesen, hängt die Identität aktueller Benutzer von der Authentifizierung und dem Identitätswechsel ab, die in der Webanwendung implementiert sind.</span><span class="sxs-lookup"><span data-stu-id="73ff8-127">When reading the registry from a Web application, the identity of current user depends on the authentication and impersonation implemented in the Web application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73ff8-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73ff8-128">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [<span data-ttu-id="73ff8-129">Lesen aus der und Schreiben in die Registrierung</span><span class="sxs-lookup"><span data-stu-id="73ff8-129">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
