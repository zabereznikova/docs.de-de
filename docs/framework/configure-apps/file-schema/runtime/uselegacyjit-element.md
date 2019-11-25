---
title: <useLegacyJit>-Element
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
ms.openlocfilehash: a126b8c0050a8d1fd96a3d090f9b018a9faa07a7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968857"
---
# <a name="uselegacyjit-element"></a><span data-ttu-id="46e87-102">\<useLegacyJit>-Element</span><span class="sxs-lookup"><span data-stu-id="46e87-102">\<useLegacyJit> Element</span></span>

<span data-ttu-id="46e87-103">Legt fest, ob die Runtime den 64-Bit-JIT-Legacycompiler für die Just-in-Time-Kompilierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="46e87-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="46e87-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="46e87-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="46e87-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="46e87-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="46e87-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<uselegacyjit >**</span><span class="sxs-lookup"><span data-stu-id="46e87-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<useLegacyJit>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e87-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="46e87-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="46e87-108">Beim Elementnamen `useLegacyJit` wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="46e87-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46e87-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="46e87-109">Attributes and elements</span></span>

<span data-ttu-id="46e87-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="46e87-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46e87-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="46e87-111">Attributes</span></span>  
  
| <span data-ttu-id="46e87-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="46e87-112">Attribute</span></span> | <span data-ttu-id="46e87-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46e87-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="46e87-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="46e87-114">Required attribute.</span></span><br><br><span data-ttu-id="46e87-115">Gibt an, ob die Laufzeit den Legacy-JIT-Compiler mit 64-Bit verwendet.</span><span class="sxs-lookup"><span data-stu-id="46e87-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="46e87-116">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="46e87-116">enabled attribute</span></span>  
  
| <span data-ttu-id="46e87-117">Wert</span><span class="sxs-lookup"><span data-stu-id="46e87-117">Value</span></span> | <span data-ttu-id="46e87-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46e87-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="46e87-119">0</span><span class="sxs-lookup"><span data-stu-id="46e87-119">0</span></span>     | <span data-ttu-id="46e87-120">Der Common Language Runtime verwendet den neuen 64-Bit-JIT-Compiler, der in der .NET Framework 4,6 und höheren Versionen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="46e87-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="46e87-121">1</span><span class="sxs-lookup"><span data-stu-id="46e87-121">1</span></span>     | <span data-ttu-id="46e87-122">Der Common Language Runtime verwendet den älteren JIT-Compiler von 64 Bit.</span><span class="sxs-lookup"><span data-stu-id="46e87-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="46e87-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="46e87-123">Child elements</span></span>

<span data-ttu-id="46e87-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="46e87-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="46e87-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="46e87-125">Parent elements</span></span>  
  
| <span data-ttu-id="46e87-126">Element</span><span class="sxs-lookup"><span data-stu-id="46e87-126">Element</span></span>         | <span data-ttu-id="46e87-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46e87-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="46e87-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="46e87-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="46e87-129">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="46e87-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="46e87-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="46e87-130">Remarks</span></span>  

<span data-ttu-id="46e87-131">Beginnend mit dem .NET Framework 4,6 verwendet die Common Language Runtime standardmäßig einen neuen 64-Bit-Compiler für die Just-in-time (JIT)-Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="46e87-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="46e87-132">In einigen Fällen kann dies zu einem Unterschied im Verhalten von Anwendungscode führen, der von der vorherigen Version des JIT-Compilers der 64-Bit-Version JIT-kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="46e87-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="46e87-133">Durch Festlegen des `enabled`-Attributs des `<useLegacyJit>`-Elements auf `1`können Sie den neuen 64-Bit-JIT-Compiler deaktivieren und stattdessen die App mithilfe des älteren 64-Bit-JIT-Compilers kompilieren.</span><span class="sxs-lookup"><span data-stu-id="46e87-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="46e87-134">Das `<useLegacyJit>` Element wirkt sich nur auf die JIT-Kompilierung 64-Bit aus.</span><span class="sxs-lookup"><span data-stu-id="46e87-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="46e87-135">Die Kompilierung mit dem 32-Bit-JIT-Compiler ist nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="46e87-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="46e87-136">Anstatt eine Konfigurationsdatei Einstellung zu verwenden, können Sie den Legacy-JIT-Compiler von 64 auf zwei weitere Arten aktivieren:</span><span class="sxs-lookup"><span data-stu-id="46e87-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="46e87-137">Festlegen einer Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="46e87-137">Setting an environment variable</span></span>

  <span data-ttu-id="46e87-138">Legen Sie für die `COMPLUS_useLegacyJit`-Umgebungsvariable entweder `0` (verwenden Sie den neuen 64-Bit-JIT-Compiler) oder `1` (verwenden Sie den älteren 64-Bit-JIT-Compiler) fest:</span><span class="sxs-lookup"><span data-stu-id="46e87-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```env  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="46e87-139">Die Umgebungsvariable verfügt über einen globalen Gültigkeits *Bereich*. Dies bedeutet, dass Sie sich auf alle auf dem Computer durchgeführten Anwendungen auswirkt.</span><span class="sxs-lookup"><span data-stu-id="46e87-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="46e87-140">Wenn diese Einstellung festgelegt ist, kann Sie von der Einstellung für die Anwendungs Konfigurationsdatei überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="46e87-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="46e87-141">Beim Namen der Umgebungsvariablen muss die Groß-/Kleinschreibung nicht beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="46e87-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="46e87-142">Hinzufügen eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="46e87-142">Adding a registry key</span></span>

  <span data-ttu-id="46e87-143">Sie können den früheren 64-Bit-JIT-Compiler aktivieren, indem Sie einen `REG_DWORD` Wert entweder zum `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` oder `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` Schlüssel in der Registrierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="46e87-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="46e87-144">Der Wert wird `useLegacyJit`benannt.</span><span class="sxs-lookup"><span data-stu-id="46e87-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="46e87-145">Wenn der Wert 0 ist, wird der neue Compiler verwendet.</span><span class="sxs-lookup"><span data-stu-id="46e87-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="46e87-146">Wenn der Wert 1 ist, ist der ältere 64-Bit-JIT-Compiler aktiviert.</span><span class="sxs-lookup"><span data-stu-id="46e87-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="46e87-147">Beim Namen des Registrierungswerts wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="46e87-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="46e87-148">Das Hinzufügen des Werts zum `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` Schlüssel wirkt sich auf alle apps aus, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="46e87-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="46e87-149">Das Hinzufügen des Werts zum `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` Schlüssel wirkt sich auf alle apps aus, die vom aktuellen Benutzer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="46e87-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="46e87-150">Wenn ein Computer mit mehreren Benutzerkonten konfiguriert ist, wirkt sich dies nur auf apps aus, die vom aktuellen Benutzer ausgeführt werden, es sei denn, der Wert wird den Registrierungs Schlüsseln für andere Benutzer ebenfalls hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="46e87-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="46e87-151">Wenn das `<useLegacyJit>`-Element einer Konfigurationsdatei hinzugefügt wird, überschreibt es die Registrierungs Einstellungen, sofern diese vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="46e87-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46e87-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46e87-152">Example</span></span>  

<span data-ttu-id="46e87-153">Die folgende Konfigurationsdatei deaktiviert die Kompilierung mit dem neuen 64-Bit-JIT-Compiler und verwendet stattdessen den älteren 64-Bit-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="46e87-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46e87-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46e87-154">See also</span></span>

- [<span data-ttu-id="46e87-155">\<Lauf Zeit > Element</span><span class="sxs-lookup"><span data-stu-id="46e87-155">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="46e87-156">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="46e87-156">\<configuration> Element</span></span>](../configuration-element.md)
- [<span data-ttu-id="46e87-157">Entschärfung: Neuer 64-Bit-JIT-Compiler</span><span class="sxs-lookup"><span data-stu-id="46e87-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
