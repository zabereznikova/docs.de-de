---
title: 'Gewusst wie: Erstellen eines Schlüssels in der Registrierung (Visual C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: f2b2cfcb09dc0c8c4d65b64f5de55c0b72746457
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2018
ms.locfileid: "42752114"
---
# <a name="how-to-create-a-key-in-the-registry-visual-c"></a><span data-ttu-id="cf9a3-102">Gewusst wie: Erstellen eines Schlüssels in der Registrierung (Visual C#)</span><span class="sxs-lookup"><span data-stu-id="cf9a3-102">How to: Create a Key In the Registry (Visual C#)</span></span>
<span data-ttu-id="cf9a3-103">Dieses Beispiel fügt der Registrierung des aktuellen Benutzers unter dem Schlüssel "Names" das Wertepaar "Name" und "Isabella" hinzu.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-103">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf9a3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cf9a3-104">Example</span></span>  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cf9a3-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="cf9a3-105">Compiling the Code</span></span>  
  
-   <span data-ttu-id="cf9a3-106">Kopieren Sie den Code, und fügen Sie ihn in die `Main`-Methode einer Konsolenanwendung ein.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-106">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
-   <span data-ttu-id="cf9a3-107">Ersetzen Sie den `Names`-Parameter durch den Namen eines Schlüssels, der sich in der Registrierung direkt unter dem HKEY_CURRENT_USER-Knoten befindet.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-107">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
-   <span data-ttu-id="cf9a3-108">Ersetzen Sie den `Name`-Parameter durch den Namen eines Werts, der sich direkt unterhalb des Names-Knotens befindet.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-108">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cf9a3-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="cf9a3-109">Robust Programming</span></span>  
 <span data-ttu-id="cf9a3-110">Untersuchen Sie die Registrierungsstruktur, um eine adäquate Position für den Schlüssel zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-110">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="cf9a3-111">Sie können beispielsweise den Schlüssel Software des aktuellen Benutzers öffnen und einen Schlüssel mit dem Namen Ihres Unternehmens erstellen.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-111">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="cf9a3-112">Anschließend fügen Sie die Registrierungswerte dem Schlüssel für das Unternehmen hinzu.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-112">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="cf9a3-113">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="cf9a3-113">The following conditions might cause an exception:</span></span>  
  
-   <span data-ttu-id="cf9a3-114">Der Name des Schlüssels ist NULL.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-114">The name of the key is null.</span></span>  
  
-   <span data-ttu-id="cf9a3-115">Der Benutzer ist nicht zum Erstellen von Registrierungsschlüsseln berechtigt.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-115">The user does not have permissions to create registry keys.</span></span>  
  
-   <span data-ttu-id="cf9a3-116">Der Name des Schlüssels ist länger als 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-116">The key name exceeds the 255-character limit.</span></span>  
  
-   <span data-ttu-id="cf9a3-117">Der Schlüssel ist geschlossen.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-117">The key is closed.</span></span>  
  
-   <span data-ttu-id="cf9a3-118">Der Registrierungsschlüssel ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-118">The registry key is read-only.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="cf9a3-119">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cf9a3-119">.NET Framework Security</span></span>  
 <span data-ttu-id="cf9a3-120">Es ist sicherer, die Daten in den Benutzerordner (`Microsoft.Win32.Registry.CurrentUser`) anstatt auf den lokalen Computer (`Microsoft.Win32.Registry.LocalMachine`) zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-120">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="cf9a3-121">Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-121">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="cf9a3-122">Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-122">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="cf9a3-123">Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-123">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="cf9a3-124">Um dies zu verhindern, verwenden Sie die `Overload:Microsoft.Win32.RegistryKey.GetValue`-</span><span class="sxs-lookup"><span data-stu-id="cf9a3-124">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="cf9a3-125">-Methode.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-125">method.</span></span> <span data-ttu-id="cf9a3-126">Die Methode gibt NULL zurück, wenn der Schlüssel noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-126">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="cf9a3-127">Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als Klartext zu speichern. Dies gilt auch, wenn der Registrierungsschlüssel durch Zugriffssteuerungslisten (ACLs) geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="cf9a3-127">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf9a3-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf9a3-128">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="cf9a3-129">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cf9a3-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cf9a3-130">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="cf9a3-130">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)  
 [<span data-ttu-id="cf9a3-131">Read, write and delete from the registry with C# (Ausführen von Aktionen in der Registrierung mit C#: Lesen, Schreiben und Löschen)</span><span class="sxs-lookup"><span data-stu-id="cf9a3-131">Read, write and delete from the registry with C#</span></span>](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)
