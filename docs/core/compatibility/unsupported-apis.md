---
title: Nicht unterstützte APIs in .NET Core
titleSuffix: ''
description: Erfahren Sie, welche APIs aus .NET Framework immer eine Ausnahme in .NET Core auslösen.
ms.date: 12/23/2019
ms.openlocfilehash: c4b94321d30cacd90d5c2ee23c258681683a6faa
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092966"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="1a956-103">APIs, die in .NET Core immer Ausnahmen auslösen</span><span class="sxs-lookup"><span data-stu-id="1a956-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="1a956-104">Die folgenden APIs lösen für .NET Core auf allen oder einer Teilmenge aller Plattformen immer die Ausnahme <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="1a956-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="1a956-105">In diesem Artikel werden die betroffenen API-Member nach Namespace organisiert.</span><span class="sxs-lookup"><span data-stu-id="1a956-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="1a956-106">Dies ist nicht die endgültige Fassung dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="1a956-106">This article is a work-in-progress.</span></span> <span data-ttu-id="1a956-107">Er enthält keine vollständige Liste der APIs, die Ausnahmen in .NET Core auslösen.</span><span class="sxs-lookup"><span data-stu-id="1a956-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="1a956-108">In diesem Artikel sind die expliziten Schnittstellenimplementierungen für die binäre Serialisierung, die in .NET Core eine Ausnahme auslösen, nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a956-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="1a956-109">Weitere Informationen finden Sie unter [Binäre Serialisierung](../../standard/serialization/binary-serialization.md#net-core).</span><span class="sxs-lookup"><span data-stu-id="1a956-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="1a956-110">System</span><span class="sxs-lookup"><span data-stu-id="1a956-110">System</span></span>

| <span data-ttu-id="1a956-111">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-111">Member</span></span> | <span data-ttu-id="1a956-112">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-113">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="1a956-114">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="1a956-115">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="1a956-116">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-117">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="1a956-118">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="1a956-119">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="1a956-120">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-121">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="1a956-122">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="1a956-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="1a956-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="1a956-124">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-124">Member</span></span> | <span data-ttu-id="1a956-125">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-126">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-127">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-128">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="1a956-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="1a956-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="1a956-130">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-130">Member</span></span> | <span data-ttu-id="1a956-131">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-132">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-133">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="1a956-134">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="1a956-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="1a956-135">System.Configuration</span></span>

| <span data-ttu-id="1a956-136">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-136">Member</span></span> | <span data-ttu-id="1a956-137">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="1a956-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (alle Member)</span><span class="sxs-lookup"><span data-stu-id="1a956-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="1a956-139">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="1a956-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="1a956-140">System.Console</span></span>

| <span data-ttu-id="1a956-141">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-141">Member</span></span> | <span data-ttu-id="1a956-142">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="1a956-143">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-143">Linux and macOS</span></span> |
| <span data-ttu-id="1a956-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-145">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-145">Linux and macOS</span></span> |
| <span data-ttu-id="1a956-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-147">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-147">Linux and macOS</span></span> |
| <span data-ttu-id="1a956-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-149">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-149">Linux and macOS</span></span> |
| <span data-ttu-id="1a956-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (nur „get“)</span><span class="sxs-lookup"><span data-stu-id="1a956-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="1a956-151">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-152">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-153">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-154">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-154">Linux and macOS</span></span> |
| <span data-ttu-id="1a956-155"><xref:System.Console.Title?displayProperty=nameWithType> (nur „get“)</span><span class="sxs-lookup"><span data-stu-id="1a956-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="1a956-156">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-156">Linux and macOS</span></span> |
| <span data-ttu-id="1a956-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-158">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-158">Linux and macOS</span></span> |
| <span data-ttu-id="1a956-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-160">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-160">Linux and macOS</span></span> |
| <span data-ttu-id="1a956-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-162">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-162">Linux and macOS</span></span> |
| <span data-ttu-id="1a956-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-164">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="1a956-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="1a956-165">System.Data.Common</span></span>

| <span data-ttu-id="1a956-166">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-166">Member</span></span> | <span data-ttu-id="1a956-167">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="1a956-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (löst <xref:System.NotSupportedException> aus)</span><span class="sxs-lookup"><span data-stu-id="1a956-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="1a956-169">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="1a956-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="1a956-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="1a956-171">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-171">Member</span></span> | <span data-ttu-id="1a956-172">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="1a956-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-174">Linux</span><span class="sxs-lookup"><span data-stu-id="1a956-174">Linux</span></span> |
| <span data-ttu-id="1a956-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-176">Linux</span><span class="sxs-lookup"><span data-stu-id="1a956-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="1a956-177">macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="1a956-178">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-179">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="1a956-180">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="1a956-181">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="1a956-182">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="1a956-183">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-183">Linux and macOS</span></span> |
| <span data-ttu-id="1a956-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-185">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-185">Linux and macOS</span></span> |
| <span data-ttu-id="1a956-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (nur „get“)</span><span class="sxs-lookup"><span data-stu-id="1a956-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="1a956-187">macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-187">macOS</span></span> |
| <span data-ttu-id="1a956-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-189">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="1a956-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="1a956-190">System.IO</span></span>

| <span data-ttu-id="1a956-191">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-191">Member</span></span> | <span data-ttu-id="1a956-192">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-193">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-194">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="1a956-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="1a956-195">System.IO.Pipes</span></span>

| <span data-ttu-id="1a956-196">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-196">Member</span></span> | <span data-ttu-id="1a956-197">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="1a956-198">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="1a956-199">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="1a956-200">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="1a956-201">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-201">Linux and macOS</span></span> |
| <span data-ttu-id="1a956-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-203">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="1a956-204">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="1a956-205">System. Media</span><span class="sxs-lookup"><span data-stu-id="1a956-205">System.Media</span></span>

| <span data-ttu-id="1a956-206">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-206">Member</span></span> | <span data-ttu-id="1a956-207">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-208">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="1a956-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="1a956-209">System.Net</span></span>

| <span data-ttu-id="1a956-210">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-210">Member</span></span> | <span data-ttu-id="1a956-211">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="1a956-212">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="1a956-213">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-214">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-215">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-216">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-217">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-218">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-219">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-220">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-221">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-222">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="1a956-223">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-224">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-225">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-226">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-227">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-228">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="1a956-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="1a956-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="1a956-230">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-230">Member</span></span> | <span data-ttu-id="1a956-231">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="1a956-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="1a956-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="1a956-233">System.Net.Sockets</span></span>

| <span data-ttu-id="1a956-234">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-234">Member</span></span> | <span data-ttu-id="1a956-235">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)?displayProperty=nameWithType> | <span data-ttu-id="1a956-236">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="1a956-237">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="1a956-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="1a956-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="1a956-239">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-239">Member</span></span> | <span data-ttu-id="1a956-240">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="1a956-241">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="1a956-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="1a956-242">System.Reflection</span></span>

| <span data-ttu-id="1a956-243">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-243">Member</span></span> | <span data-ttu-id="1a956-244">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-245">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="1a956-246">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-247">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="1a956-248">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="1a956-249">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-250">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="1a956-251">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="1a956-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="1a956-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="1a956-253">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-253">Member</span></span> | <span data-ttu-id="1a956-254">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="1a956-255">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="1a956-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="1a956-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="1a956-257">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-257">Member</span></span> | <span data-ttu-id="1a956-258">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="1a956-259">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="1a956-260">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="1a956-261">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="1a956-262">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="1a956-263">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="1a956-264">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="1a956-265">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="1a956-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="1a956-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="1a956-267">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-267">Member</span></span> | <span data-ttu-id="1a956-268">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="1a956-269">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="1a956-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="1a956-270">System.Security</span></span>

| <span data-ttu-id="1a956-271">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-271">Member</span></span> | <span data-ttu-id="1a956-272">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="1a956-273">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="1a956-274">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="1a956-275">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="1a956-276">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="1a956-277">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="1a956-278">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="1a956-279">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="1a956-280">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="1a956-281">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="1a956-282">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="1a956-283">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="1a956-284">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="1a956-285">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="1a956-286">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="1a956-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="1a956-287">System.Security.Claims</span></span>

| <span data-ttu-id="1a956-288">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-288">Member</span></span> | <span data-ttu-id="1a956-289">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="1a956-290">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-291">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="1a956-292">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-293">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-294">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="1a956-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="1a956-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="1a956-296">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-296">Member</span></span> | <span data-ttu-id="1a956-297">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="1a956-298">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-299">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="1a956-300">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="1a956-301">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="1a956-302">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="1a956-303">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="1a956-304">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="1a956-305">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="1a956-306">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="1a956-307">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="1a956-308">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="1a956-309">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="1a956-310">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="1a956-311">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="1a956-312">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="1a956-313">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="1a956-314">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-315">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-316">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-317">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="1a956-318">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="1a956-319">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-320">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-321">Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="1a956-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-322">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-323">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="1a956-324">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="1a956-325">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="1a956-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="1a956-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="1a956-327">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-327">Member</span></span> | <span data-ttu-id="1a956-328">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="1a956-329">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="1a956-330">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="1a956-331">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="1a956-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="1a956-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="1a956-333">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-333">Member</span></span> | <span data-ttu-id="1a956-334">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-335">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-336">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-337">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-337">All</span></span> |
| <span data-ttu-id="1a956-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (nur „set“)</span><span class="sxs-lookup"><span data-stu-id="1a956-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="1a956-339">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="1a956-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="1a956-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="1a956-341">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-341">Member</span></span> | <span data-ttu-id="1a956-342">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-343">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="1a956-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="1a956-344">System.Security.Policy</span></span>

| <span data-ttu-id="1a956-345">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-345">Member</span></span> | <span data-ttu-id="1a956-346">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-347">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="1a956-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="1a956-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="1a956-349">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-349">Member</span></span> | <span data-ttu-id="1a956-350">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-351">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="1a956-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="1a956-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="1a956-353">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-353">Member</span></span> | <span data-ttu-id="1a956-354">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-355">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="1a956-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="1a956-356">System.Threading</span></span>

| <span data-ttu-id="1a956-357">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-357">Member</span></span> | <span data-ttu-id="1a956-358">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-359">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="1a956-360">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="1a956-361">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="1a956-362">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="1a956-363">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="1a956-364">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="1a956-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="1a956-365">System.Xml</span></span>

| <span data-ttu-id="1a956-366">Member</span><span class="sxs-lookup"><span data-stu-id="1a956-366">Member</span></span> | <span data-ttu-id="1a956-367">Plattformen, auf denen eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="1a956-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="1a956-368">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="1a956-369">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="1a956-370">Alle</span><span class="sxs-lookup"><span data-stu-id="1a956-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="1a956-371">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a956-371">See also</span></span>

- [<span data-ttu-id="1a956-372">Breaking Changes für die Migration von .NET Framework 3.0 zu .NET Core</span><span class="sxs-lookup"><span data-stu-id="1a956-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="1a956-373">Binäre Serialisierung in .NET Core</span><span class="sxs-lookup"><span data-stu-id="1a956-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="1a956-374">.NET Portability Analyzer</span><span class="sxs-lookup"><span data-stu-id="1a956-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
