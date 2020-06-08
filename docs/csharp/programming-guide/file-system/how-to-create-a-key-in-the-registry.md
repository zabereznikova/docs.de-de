---
title: 'Vorgehensweise: Erstellen eines Schlüssels in der Registrierung (C#- Programmierleitfaden)'
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: 9e340083ffca118337dc9a53bdf20808cd1b15cb
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241629"
---
# <a name="how-to-create-a-key-in-the-registry-c-programming-guide"></a><span data-ttu-id="c78c9-102">Vorgehensweise: Erstellen eines Schlüssels in der Registrierung (C#- Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="c78c9-102">How to create a key in the registry (C# Programming Guide)</span></span>
<span data-ttu-id="c78c9-103">Dieses Beispiel fügt der Registrierung des aktuellen Benutzers unter dem Schlüssel "Names" das Wertepaar "Name" und "Isabella" hinzu.</span><span class="sxs-lookup"><span data-stu-id="c78c9-103">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="c78c9-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c78c9-104">Example</span></span>  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c78c9-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c78c9-105">Compiling the Code</span></span>  
  
- <span data-ttu-id="c78c9-106">Kopieren Sie den Code, und fügen Sie ihn in die `Main`-Methode einer Konsolenanwendung ein.</span><span class="sxs-lookup"><span data-stu-id="c78c9-106">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
- <span data-ttu-id="c78c9-107">Ersetzen Sie den `Names`-Parameter durch den Namen eines Schlüssels, der sich in der Registrierung direkt unter dem HKEY_CURRENT_USER-Knoten befindet.</span><span class="sxs-lookup"><span data-stu-id="c78c9-107">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
- <span data-ttu-id="c78c9-108">Ersetzen Sie den `Name`-Parameter durch den Namen eines Werts, der sich direkt unterhalb des Names-Knotens befindet.</span><span class="sxs-lookup"><span data-stu-id="c78c9-108">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c78c9-109">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="c78c9-109">Robust Programming</span></span>  
 <span data-ttu-id="c78c9-110">Untersuchen Sie die Registrierungsstruktur, um eine adäquate Position für den Schlüssel zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c78c9-110">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="c78c9-111">Sie können beispielsweise den Schlüssel Software des aktuellen Benutzers öffnen und einen Schlüssel mit dem Namen Ihres Unternehmens erstellen.</span><span class="sxs-lookup"><span data-stu-id="c78c9-111">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="c78c9-112">Anschließend fügen Sie die Registrierungswerte dem Schlüssel für das Unternehmen hinzu.</span><span class="sxs-lookup"><span data-stu-id="c78c9-112">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="c78c9-113">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="c78c9-113">The following conditions might cause an exception:</span></span>  
  
- <span data-ttu-id="c78c9-114">Der Name des Schlüssels ist NULL.</span><span class="sxs-lookup"><span data-stu-id="c78c9-114">The name of the key is null.</span></span>  
  
- <span data-ttu-id="c78c9-115">Der Benutzer ist nicht zum Erstellen von Registrierungsschlüsseln berechtigt.</span><span class="sxs-lookup"><span data-stu-id="c78c9-115">The user does not have permissions to create registry keys.</span></span>  
  
- <span data-ttu-id="c78c9-116">Der Name des Schlüssels ist länger als 255 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c78c9-116">The key name exceeds the 255-character limit.</span></span>  
  
- <span data-ttu-id="c78c9-117">Der Schlüssel ist geschlossen.</span><span class="sxs-lookup"><span data-stu-id="c78c9-117">The key is closed.</span></span>  
  
- <span data-ttu-id="c78c9-118">Der Registrierungsschlüssel ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="c78c9-118">The registry key is read-only.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="c78c9-119">.NET-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c78c9-119">.NET Security</span></span>  
 <span data-ttu-id="c78c9-120">Es ist sicherer, die Daten in den Benutzerordner (`Microsoft.Win32.Registry.CurrentUser`) anstatt auf den lokalen Computer (`Microsoft.Win32.Registry.LocalMachine`) zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="c78c9-120">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="c78c9-121">Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c78c9-121">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="c78c9-122">Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="c78c9-122">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="c78c9-123">Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c78c9-123">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="c78c9-124">Um dies zu verhindern, verwenden Sie die `Overload:Microsoft.Win32.RegistryKey.GetValue`-</span><span class="sxs-lookup"><span data-stu-id="c78c9-124">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="c78c9-125">-Methode.</span><span class="sxs-lookup"><span data-stu-id="c78c9-125">method.</span></span> <span data-ttu-id="c78c9-126">Die Methode gibt NULL zurück, wenn der Schlüssel noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c78c9-126">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="c78c9-127">Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als Klartext zu speichern. Dies gilt auch, wenn der Registrierungsschlüssel durch Zugriffssteuerungslisten (ACLs) geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="c78c9-127">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c78c9-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c78c9-128">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="c78c9-129">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c78c9-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c78c9-130">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c78c9-130">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="c78c9-131">Read, write and delete from the registry with C# (Ausführen von Aktionen in der Registrierung mit C#: Lesen, Schreiben und Löschen)</span><span class="sxs-lookup"><span data-stu-id="c78c9-131">Read, write and delete from the registry with C#</span></span>](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)
