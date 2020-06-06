---
title: <useLegacyJit>-Element
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
ms.openlocfilehash: a126b8c0050a8d1fd96a3d090f9b018a9faa07a7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968857"
---
# <a name="uselegacyjit-element"></a><span data-ttu-id="3fc57-102">\<useLegacyJit>-Element</span><span class="sxs-lookup"><span data-stu-id="3fc57-102">\<useLegacyJit> Element</span></span>

<span data-ttu-id="3fc57-103">Legt fest, ob die Runtime den 64-Bit-JIT-Legacycompiler für die Just-in-Time-Kompilierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3fc57-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<useLegacyJit>**  
  
## <a name="syntax"></a><span data-ttu-id="3fc57-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fc57-104">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="3fc57-105">Beim Elementnamen `useLegacyJit` wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="3fc57-105">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fc57-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3fc57-106">Attributes and elements</span></span>

<span data-ttu-id="3fc57-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3fc57-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fc57-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="3fc57-108">Attributes</span></span>  
  
| <span data-ttu-id="3fc57-109">attribute</span><span class="sxs-lookup"><span data-stu-id="3fc57-109">Attribute</span></span> | <span data-ttu-id="3fc57-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3fc57-110">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="3fc57-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="3fc57-111">Required attribute.</span></span><br><br><span data-ttu-id="3fc57-112">Gibt an, ob die Laufzeit den Legacy-JIT-Compiler mit 64-Bit verwendet.</span><span class="sxs-lookup"><span data-stu-id="3fc57-112">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="3fc57-113">aktiviertes Attribut</span><span class="sxs-lookup"><span data-stu-id="3fc57-113">enabled attribute</span></span>  
  
| <span data-ttu-id="3fc57-114">Wert</span><span class="sxs-lookup"><span data-stu-id="3fc57-114">Value</span></span> | <span data-ttu-id="3fc57-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3fc57-115">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="3fc57-116">0</span><span class="sxs-lookup"><span data-stu-id="3fc57-116">0</span></span>     | <span data-ttu-id="3fc57-117">Der Common Language Runtime verwendet den neuen 64-Bit-JIT-Compiler, der in der .NET Framework 4,6 und höheren Versionen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3fc57-117">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="3fc57-118">1</span><span class="sxs-lookup"><span data-stu-id="3fc57-118">1</span></span>     | <span data-ttu-id="3fc57-119">Der Common Language Runtime verwendet den älteren JIT-Compiler von 64 Bit.</span><span class="sxs-lookup"><span data-stu-id="3fc57-119">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="3fc57-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3fc57-120">Child elements</span></span>

<span data-ttu-id="3fc57-121">Keine</span><span class="sxs-lookup"><span data-stu-id="3fc57-121">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="3fc57-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3fc57-122">Parent elements</span></span>  
  
| <span data-ttu-id="3fc57-123">Element</span><span class="sxs-lookup"><span data-stu-id="3fc57-123">Element</span></span>         | <span data-ttu-id="3fc57-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3fc57-124">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="3fc57-125">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="3fc57-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="3fc57-126">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="3fc57-126">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="3fc57-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3fc57-127">Remarks</span></span>  

<span data-ttu-id="3fc57-128">Beginnend mit dem .NET Framework 4,6 verwendet die Common Language Runtime standardmäßig einen neuen 64-Bit-Compiler für die Just-in-time (JIT)-Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="3fc57-128">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="3fc57-129">In einigen Fällen kann dies zu einem Unterschied im Verhalten von Anwendungscode führen, der von der vorherigen Version des JIT-Compilers der 64-Bit-Version JIT-kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="3fc57-129">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="3fc57-130">Indem Sie das- `enabled` Attribut des- `<useLegacyJit>` Elements auf festlegen `1` , können Sie den neuen 64-Bit-JIT-Compiler deaktivieren und stattdessen die App mithilfe des Legacy-JIT-Compilers (64-Bit) kompilieren.</span><span class="sxs-lookup"><span data-stu-id="3fc57-130">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3fc57-131">Das `<useLegacyJit>` Element wirkt sich nur auf die JIT-Kompilierung 64-Bit aus</span><span class="sxs-lookup"><span data-stu-id="3fc57-131">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="3fc57-132">Die Kompilierung mit dem 32-Bit-JIT-Compiler ist nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="3fc57-132">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="3fc57-133">Anstatt eine Konfigurationsdatei Einstellung zu verwenden, können Sie den Legacy-JIT-Compiler von 64 auf zwei weitere Arten aktivieren:</span><span class="sxs-lookup"><span data-stu-id="3fc57-133">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="3fc57-134">Festlegen einer Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="3fc57-134">Setting an environment variable</span></span>

  <span data-ttu-id="3fc57-135">Legen `COMPLUS_useLegacyJit` Sie die Umgebungsvariable entweder auf `0` (verwenden Sie den neuen 64-Bit-JIT-Compiler) oder `1` (verwenden Sie den älteren 64-Bit-JIT-Compiler):</span><span class="sxs-lookup"><span data-stu-id="3fc57-135">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```env  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="3fc57-136">Die Umgebungsvariable verfügt über einen globalen Gültigkeits *Bereich*. Dies bedeutet, dass Sie sich auf alle auf dem Computer durchgeführten Anwendungen auswirkt.</span><span class="sxs-lookup"><span data-stu-id="3fc57-136">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="3fc57-137">Wenn diese Einstellung festgelegt ist, kann Sie von der Einstellung für die Anwendungs Konfigurationsdatei überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="3fc57-137">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="3fc57-138">Beim Namen der Umgebungsvariablen muss die Groß-/Kleinschreibung nicht beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="3fc57-138">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="3fc57-139">Hinzufügen eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="3fc57-139">Adding a registry key</span></span>

  <span data-ttu-id="3fc57-140">Sie können den Legacy-JIT-Compiler von 64 aktivieren, indem Sie `REG_DWORD` dem-oder- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` Schlüssel in der Registrierung einen-Wert hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3fc57-140">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="3fc57-141">Der Wert hat den Namen `useLegacyJit` .</span><span class="sxs-lookup"><span data-stu-id="3fc57-141">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="3fc57-142">Wenn der Wert 0 ist, wird der neue Compiler verwendet.</span><span class="sxs-lookup"><span data-stu-id="3fc57-142">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="3fc57-143">Wenn der Wert 1 ist, ist der ältere 64-Bit-JIT-Compiler aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3fc57-143">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="3fc57-144">Beim Namen des Registrierungswerts wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="3fc57-144">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="3fc57-145">Das Hinzufügen des Werts zum `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` Schlüssel betrifft alle apps, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3fc57-145">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="3fc57-146">Das Hinzufügen des Werts zum `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` Schlüssel wirkt sich auf alle apps aus, die vom aktuellen Benutzer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3fc57-146">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="3fc57-147">Wenn ein Computer mit mehreren Benutzerkonten konfiguriert ist, wirkt sich dies nur auf apps aus, die vom aktuellen Benutzer ausgeführt werden, es sei denn, der Wert wird den Registrierungs Schlüsseln für andere Benutzer ebenfalls hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3fc57-147">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="3fc57-148">Das Hinzufügen des- `<useLegacyJit>` Elements zu einer Konfigurationsdatei überschreibt die Registrierungs Einstellungen, sofern diese vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3fc57-148">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fc57-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fc57-149">Example</span></span>  

<span data-ttu-id="3fc57-150">Die folgende Konfigurationsdatei deaktiviert die Kompilierung mit dem neuen 64-Bit-JIT-Compiler und verwendet stattdessen den älteren 64-Bit-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="3fc57-150">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fc57-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fc57-151">See also</span></span>

- [<span data-ttu-id="3fc57-152">\<runtime>Gewisses</span><span class="sxs-lookup"><span data-stu-id="3fc57-152">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="3fc57-153">\<configuration>Gewisses</span><span class="sxs-lookup"><span data-stu-id="3fc57-153">\<configuration> Element</span></span>](../configuration-element.md)
- [<span data-ttu-id="3fc57-154">Entschärfung: Neuer 64-Bit-JIT-Compiler</span><span class="sxs-lookup"><span data-stu-id="3fc57-154">Mitigation: New 64-bit JIT Compiler</span></span>](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
