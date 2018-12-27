---
title: '&lt;UseLegacyJit&gt; Element'
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd4f9728338ecc66f84fe42b9bdbda9938ed518b
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612191"
---
# <a name="ltuselegacyjitgt-element"></a><span data-ttu-id="ecf82-102">&lt;UseLegacyJit&gt; Element</span><span class="sxs-lookup"><span data-stu-id="ecf82-102">&lt;useLegacyJit&gt; Element</span></span>

<span data-ttu-id="ecf82-103">Legt fest, ob die Runtime den 64-Bit-JIT-Legacycompiler für die Just-in-Time-Kompilierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecf82-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="ecf82-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ecf82-104">\<configuration></span></span>  
<span data-ttu-id="ecf82-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="ecf82-105">\<runtime></span></span>  
<span data-ttu-id="ecf82-106">\<UseLegacyJit ></span><span class="sxs-lookup"><span data-stu-id="ecf82-106">\<useLegacyJit></span></span>
  
## <a name="syntax"></a><span data-ttu-id="ecf82-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecf82-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="ecf82-108">Der Elementname `useLegacyJit` Groß-/Kleinschreibung beachtet wird.</span><span class="sxs-lookup"><span data-stu-id="ecf82-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecf82-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ecf82-109">Attributes and elements</span></span>

<span data-ttu-id="ecf82-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ecf82-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ecf82-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="ecf82-111">Attributes</span></span>  
  
| <span data-ttu-id="ecf82-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="ecf82-112">Attribute</span></span> | <span data-ttu-id="ecf82-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecf82-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="ecf82-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ecf82-114">Required attribute.</span></span><br><br><span data-ttu-id="ecf82-115">Gibt an, ob die Runtime die älteren 64-Bit-JIT-Compiler verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecf82-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="ecf82-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="ecf82-116">enabled attribute</span></span>  
  
| <span data-ttu-id="ecf82-117">Wert</span><span class="sxs-lookup"><span data-stu-id="ecf82-117">Value</span></span> | <span data-ttu-id="ecf82-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecf82-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="ecf82-119">0</span><span class="sxs-lookup"><span data-stu-id="ecf82-119">0</span></span>     | <span data-ttu-id="ecf82-120">Die common Language Runtime verwendet, den neuen 64-Bit-JIT-Compiler in der .NET Framework 4.6 und höheren Versionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ecf82-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="ecf82-121">1</span><span class="sxs-lookup"><span data-stu-id="ecf82-121">1</span></span>     | <span data-ttu-id="ecf82-122">Die common Language Runtime verwendet die älteren 64-Bit-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="ecf82-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="ecf82-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ecf82-123">Child elements</span></span>

<span data-ttu-id="ecf82-124">Keine</span><span class="sxs-lookup"><span data-stu-id="ecf82-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="ecf82-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ecf82-125">Parent elements</span></span>  
  
| <span data-ttu-id="ecf82-126">Element</span><span class="sxs-lookup"><span data-stu-id="ecf82-126">Element</span></span>         | <span data-ttu-id="ecf82-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecf82-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="ecf82-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ecf82-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="ecf82-129">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="ecf82-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="ecf82-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ecf82-130">Remarks</span></span>  

<span data-ttu-id="ecf82-131">Ab .NET Framework 4.6, verwendet die common Language Runtime einen neuen 64-Bit-Compiler für Just-in-Time (JIT)-Kompilierung standardmäßig möglich werden.</span><span class="sxs-lookup"><span data-stu-id="ecf82-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="ecf82-132">In einigen Fällen kann dies einen Unterschied im Verhalten von Anwendungscode führen, die von der vorherigen Version des 64-Bit-JIT-Compilers JIT-kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="ecf82-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="ecf82-133">Durch Festlegen der `enabled` Attribut der `<useLegacyJit>` Element `1`, können Sie den neuen 64-Bit-JIT-Compiler zu deaktivieren und stattdessen Ihre app mit dem älteren 64-Bit-JIT-Compiler zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="ecf82-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ecf82-134">Die `<useLegacyJit>` Element betrifft nur 64-Bit-JIT-Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="ecf82-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="ecf82-135">Kompilierung mit der 32-Bit-JIT-Compiler ist nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="ecf82-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="ecf82-136">Anstatt eine Konfigurationseinstellung für die Datei zu verwenden, können Sie den älteren 64-Bit-JIT-Compiler auf zwei weitere Arten aktivieren:</span><span class="sxs-lookup"><span data-stu-id="ecf82-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="ecf82-137">Festlegen von Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="ecf82-137">Setting an environment variable</span></span>

  <span data-ttu-id="ecf82-138">Legen Sie die `COMPLUS_useLegacyJit` Umgebungsvariable entweder `0` (verwenden Sie den neuen 64-Bit-JIT-Compiler) oder `1` (verwenden Sie die älteren 64-Bit-JIT-Compiler):</span><span class="sxs-lookup"><span data-stu-id="ecf82-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="ecf82-139">Die Umgebungsvariable hat *globalen Gültigkeitsbereich*, d. h., die sie wirkt sich auf alle Anwendungen auf dem Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecf82-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="ecf82-140">Wenn festgelegt, es durch eine Einstellung der Anwendung Konfigurationsdatei überschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="ecf82-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="ecf82-141">Der Name der Umgebungsvariablen ist nicht in der Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="ecf82-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="ecf82-142">Hinzufügen eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="ecf82-142">Adding a registry key</span></span>

  <span data-ttu-id="ecf82-143">Sie können die älteren 64-Bit-JIT-Compiler aktivieren, durch das Hinzufügen einer `REG_DWORD` Wert, der entweder die `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` oder `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` -Schlüssel in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="ecf82-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="ecf82-144">Der Wert wird als `useLegacyJit`.</span><span class="sxs-lookup"><span data-stu-id="ecf82-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="ecf82-145">Wenn der Wert 0 ist, wird der neue Compiler verwendet.</span><span class="sxs-lookup"><span data-stu-id="ecf82-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="ecf82-146">Wenn der Wert 1 ist, ist der ältere 64-Bit-JIT-Compiler aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ecf82-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="ecf82-147">Der Name des Registrierungsschlüssels wird nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="ecf82-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="ecf82-148">Hinzufügen des Werts, der die `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` Schlüssel wirkt sich auf alle apps, die auf dem Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecf82-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="ecf82-149">Hinzufügen des Werts, der die `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` Schlüssel wirkt sich auf alle apps, die vom aktuellen Benutzer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ecf82-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="ecf82-150">Wenn ein Computer mit mehreren Benutzerkonten konfiguriert ist, sind nur apps, die vom aktuellen Benutzer ausgeführt betroffen, es sei denn, die Registrierungsschlüssel für andere Benutzer als auch der Wert hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="ecf82-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="ecf82-151">Hinzufügen der `<useLegacyJit>` Elements zu einer Konfigurationsdatei überschreibt die registrierungseinstellungen aus, wenn sie vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ecf82-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecf82-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ecf82-152">Example</span></span>  

<span data-ttu-id="ecf82-153">Die folgende Konfigurationsdatei deaktiviert die Kompilierung mit dem neuen 64-Bit-JIT-Compiler und verwendet stattdessen die älteren 64-Bit-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="ecf82-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ecf82-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecf82-154">See also</span></span>

- [<span data-ttu-id="ecf82-155">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="ecf82-155">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)   
- [<span data-ttu-id="ecf82-156">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="ecf82-156">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)   
- [<span data-ttu-id="ecf82-157">Entschärfung: Neue 64-Bit-JIT-Compiler</span><span class="sxs-lookup"><span data-stu-id="ecf82-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
