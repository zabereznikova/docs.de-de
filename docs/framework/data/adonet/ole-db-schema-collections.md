---
title: OLE DB-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 2d5718c12100ebea49a6b6fab29a3790918c6ad3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783449"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="04e58-102">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="04e58-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="04e58-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="04e58-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="04e58-104">Microsoft SQL Server-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="04e58-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="04e58-105">Der Microsoft SQL Server OLE DB-Treibers unterstützt zusätzlich zu den allgemeinen Schema Auflistungen auch die folgenden spezifischen Schema Auflistungen:</span><span class="sxs-lookup"><span data-stu-id="04e58-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="04e58-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="04e58-106">Tables</span></span>  
  
- <span data-ttu-id="04e58-107">Spalten</span><span class="sxs-lookup"><span data-stu-id="04e58-107">Columns</span></span>  
  
- <span data-ttu-id="04e58-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="04e58-108">Procedures</span></span>  
  
- <span data-ttu-id="04e58-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="04e58-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="04e58-110">Katalog</span><span class="sxs-lookup"><span data-stu-id="04e58-110">Catalog</span></span>  
  
- <span data-ttu-id="04e58-111">Indizes</span><span class="sxs-lookup"><span data-stu-id="04e58-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="04e58-112">Tabellen</span><span class="sxs-lookup"><span data-stu-id="04e58-112">Tables</span></span>  
  
|<span data-ttu-id="04e58-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-113">ColumnName</span></span>|<span data-ttu-id="04e58-114">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-115">TABLE_CATALOG</span></span>|<span data-ttu-id="04e58-116">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-116">String</span></span>|  
|<span data-ttu-id="04e58-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="04e58-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-118">String</span></span>|  
|<span data-ttu-id="04e58-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-119">TABLE_NAME</span></span>|<span data-ttu-id="04e58-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-120">String</span></span>|  
|<span data-ttu-id="04e58-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-121">TABLE_TYPE</span></span>|<span data-ttu-id="04e58-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-122">String</span></span>|  
|<span data-ttu-id="04e58-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-123">TABLE_GUID</span></span>|<span data-ttu-id="04e58-124">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-124">Guid</span></span>|  
|<span data-ttu-id="04e58-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-125">DESCRIPTION</span></span>|<span data-ttu-id="04e58-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-126">String</span></span>|  
|<span data-ttu-id="04e58-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="04e58-127">TABLE_PROPID</span></span>|<span data-ttu-id="04e58-128">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-128">Int64</span></span>|  
|<span data-ttu-id="04e58-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="04e58-129">DATE_CREATED</span></span>|<span data-ttu-id="04e58-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-130">DateTime</span></span>|  
|<span data-ttu-id="04e58-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="04e58-131">DATE_MODIFIED</span></span>|<span data-ttu-id="04e58-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="04e58-133">Spalten</span><span class="sxs-lookup"><span data-stu-id="04e58-133">Columns</span></span>  
  
|<span data-ttu-id="04e58-134">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-134">ColumnName</span></span>|<span data-ttu-id="04e58-135">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-136">TABLE_CATALOG</span></span>|<span data-ttu-id="04e58-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-137">String</span></span>|  
|<span data-ttu-id="04e58-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="04e58-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-139">String</span></span>|  
|<span data-ttu-id="04e58-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-140">TABLE_NAME</span></span>|<span data-ttu-id="04e58-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-141">String</span></span>|  
|<span data-ttu-id="04e58-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-142">COLUMN_NAME</span></span>|<span data-ttu-id="04e58-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-143">String</span></span>|  
|<span data-ttu-id="04e58-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-144">COLUMN_GUID</span></span>|<span data-ttu-id="04e58-145">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-145">Guid</span></span>|  
|<span data-ttu-id="04e58-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="04e58-146">COLUMN_PROPID</span></span>|<span data-ttu-id="04e58-147">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-147">Int64</span></span>|  
|<span data-ttu-id="04e58-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="04e58-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="04e58-149">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-149">Int64</span></span>|  
|<span data-ttu-id="04e58-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="04e58-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="04e58-151">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-151">Boolean</span></span>|  
|<span data-ttu-id="04e58-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="04e58-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="04e58-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-153">String</span></span>|  
|<span data-ttu-id="04e58-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="04e58-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="04e58-155">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-155">Int64</span></span>|  
|<span data-ttu-id="04e58-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="04e58-156">IS_NULLABLE</span></span>|<span data-ttu-id="04e58-157">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-157">Boolean</span></span>|  
|<span data-ttu-id="04e58-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-158">DATA_TYPE</span></span>|<span data-ttu-id="04e58-159">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-159">Int32</span></span>|  
|<span data-ttu-id="04e58-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-160">TYPE_GUID</span></span>|<span data-ttu-id="04e58-161">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-161">Guid</span></span>|  
|<span data-ttu-id="04e58-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="04e58-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="04e58-163">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-163">Int64</span></span>|  
|<span data-ttu-id="04e58-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="04e58-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="04e58-165">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-165">Int64</span></span>|  
|<span data-ttu-id="04e58-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="04e58-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="04e58-167">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-167">Int32</span></span>|  
|<span data-ttu-id="04e58-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="04e58-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="04e58-169">Int16</span><span class="sxs-lookup"><span data-stu-id="04e58-169">Int16</span></span>|  
|<span data-ttu-id="04e58-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="04e58-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="04e58-171">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-171">Int64</span></span>|  
|<span data-ttu-id="04e58-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="04e58-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-173">String</span></span>|  
|<span data-ttu-id="04e58-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="04e58-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-175">String</span></span>|  
|<span data-ttu-id="04e58-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="04e58-177">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-177">String</span></span>|  
|<span data-ttu-id="04e58-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="04e58-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-179">String</span></span>|  
|<span data-ttu-id="04e58-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="04e58-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-181">String</span></span>|  
|<span data-ttu-id="04e58-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-182">COLLATION_NAME</span></span>|<span data-ttu-id="04e58-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-183">String</span></span>|  
|<span data-ttu-id="04e58-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="04e58-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-185">String</span></span>|  
|<span data-ttu-id="04e58-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="04e58-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-187">String</span></span>|  
|<span data-ttu-id="04e58-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-188">DOMAIN_NAME</span></span>|<span data-ttu-id="04e58-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-189">String</span></span>|  
|<span data-ttu-id="04e58-190">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-190">DESCRIPTION</span></span>|<span data-ttu-id="04e58-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-191">String</span></span>|  
|<span data-ttu-id="04e58-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="04e58-192">COLUMN_LCID</span></span>|<span data-ttu-id="04e58-193">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-193">Int32</span></span>|  
|<span data-ttu-id="04e58-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="04e58-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="04e58-195">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-195">Int32</span></span>|  
|<span data-ttu-id="04e58-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="04e58-196">COLUMN_SORTID</span></span>|<span data-ttu-id="04e58-197">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-197">Int32</span></span>|  
|<span data-ttu-id="04e58-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="04e58-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="04e58-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="04e58-199">Byte[]</span></span>|  
|<span data-ttu-id="04e58-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="04e58-200">IS_COMPUTED</span></span>|<span data-ttu-id="04e58-201">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="04e58-202">Verfahren</span><span class="sxs-lookup"><span data-stu-id="04e58-202">Procedures</span></span>  
  
|<span data-ttu-id="04e58-203">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-203">ColumnName</span></span>|<span data-ttu-id="04e58-204">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="04e58-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-206">String</span></span>|  
|<span data-ttu-id="04e58-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="04e58-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-208">String</span></span>|  
|<span data-ttu-id="04e58-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="04e58-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-210">String</span></span>|  
|<span data-ttu-id="04e58-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="04e58-212">Int16</span><span class="sxs-lookup"><span data-stu-id="04e58-212">Int16</span></span>|  
|<span data-ttu-id="04e58-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="04e58-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="04e58-214">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-214">String</span></span>|  
|<span data-ttu-id="04e58-215">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-215">DESCRIPTION</span></span>|<span data-ttu-id="04e58-216">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-216">String</span></span>|  
|<span data-ttu-id="04e58-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="04e58-217">DATE_CREATED</span></span>|<span data-ttu-id="04e58-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-218">DateTime</span></span>|  
|<span data-ttu-id="04e58-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="04e58-219">DATE_MODIFIED</span></span>|<span data-ttu-id="04e58-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="04e58-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="04e58-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="04e58-222">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-222">ColumnName</span></span>|<span data-ttu-id="04e58-223">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="04e58-225">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-225">String</span></span>|  
|<span data-ttu-id="04e58-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="04e58-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-227">String</span></span>|  
|<span data-ttu-id="04e58-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="04e58-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-229">String</span></span>|  
|<span data-ttu-id="04e58-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-230">PARAMETER_NAME</span></span>|<span data-ttu-id="04e58-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-231">String</span></span>|  
|<span data-ttu-id="04e58-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="04e58-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="04e58-233">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-233">Int32</span></span>|  
|<span data-ttu-id="04e58-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="04e58-235">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-235">Int32</span></span>|  
|<span data-ttu-id="04e58-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="04e58-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="04e58-237">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-237">Boolean</span></span>|  
|<span data-ttu-id="04e58-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="04e58-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="04e58-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-239">String</span></span>|  
|<span data-ttu-id="04e58-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="04e58-240">IS_NULLABLE</span></span>|<span data-ttu-id="04e58-241">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-241">Boolean</span></span>|  
|<span data-ttu-id="04e58-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-242">DATA_TYPE</span></span>|<span data-ttu-id="04e58-243">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-243">Int32</span></span>|  
|<span data-ttu-id="04e58-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="04e58-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="04e58-245">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-245">Int64</span></span>|  
|<span data-ttu-id="04e58-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="04e58-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="04e58-247">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-247">Int64</span></span>|  
|<span data-ttu-id="04e58-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="04e58-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="04e58-249">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-249">Int32</span></span>|  
|<span data-ttu-id="04e58-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="04e58-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="04e58-251">Int16</span><span class="sxs-lookup"><span data-stu-id="04e58-251">Int16</span></span>|  
|<span data-ttu-id="04e58-252">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-252">DESCRIPTION</span></span>|<span data-ttu-id="04e58-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-253">String</span></span>|  
|<span data-ttu-id="04e58-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-254">TYPE_NAME</span></span>|<span data-ttu-id="04e58-255">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-255">String</span></span>|  
|<span data-ttu-id="04e58-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="04e58-257">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="04e58-258">Katalog</span><span class="sxs-lookup"><span data-stu-id="04e58-258">Catalog</span></span>  
  
|<span data-ttu-id="04e58-259">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-259">ColumnName</span></span>|<span data-ttu-id="04e58-260">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-261">CATALOG_NAME</span></span>|<span data-ttu-id="04e58-262">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-262">String</span></span>|  
|<span data-ttu-id="04e58-263">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-263">DESCRIPTION</span></span>|<span data-ttu-id="04e58-264">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="04e58-265">Indizes</span><span class="sxs-lookup"><span data-stu-id="04e58-265">Indexes</span></span>  
  
|<span data-ttu-id="04e58-266">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-266">ColumnName</span></span>|<span data-ttu-id="04e58-267">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-268">TABLE_CATALOG</span></span>|<span data-ttu-id="04e58-269">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-269">String</span></span>|  
|<span data-ttu-id="04e58-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="04e58-271">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-271">String</span></span>|  
|<span data-ttu-id="04e58-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-272">TABLE_NAME</span></span>|<span data-ttu-id="04e58-273">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-273">String</span></span>|  
|<span data-ttu-id="04e58-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-274">INDEX_CATALOG</span></span>|<span data-ttu-id="04e58-275">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-275">String</span></span>|  
|<span data-ttu-id="04e58-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="04e58-277">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-277">String</span></span>|  
|<span data-ttu-id="04e58-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-278">INDEX_NAME</span></span>|<span data-ttu-id="04e58-279">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-279">String</span></span>|  
|<span data-ttu-id="04e58-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="04e58-280">PRIMARY_KEY</span></span>|<span data-ttu-id="04e58-281">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-281">Boolean</span></span>|  
|<span data-ttu-id="04e58-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="04e58-282">UNIQUE</span></span>|<span data-ttu-id="04e58-283">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-283">Boolean</span></span>|  
|<span data-ttu-id="04e58-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="04e58-284">CLUSTERED</span></span>|<span data-ttu-id="04e58-285">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-285">Boolean</span></span>|  
|<span data-ttu-id="04e58-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-286">TYPE</span></span>|<span data-ttu-id="04e58-287">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-287">Int32</span></span>|  
|<span data-ttu-id="04e58-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="04e58-288">FILL_FACTOR</span></span>|<span data-ttu-id="04e58-289">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-289">Int32</span></span>|  
|<span data-ttu-id="04e58-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="04e58-290">INITIAL_SIZE</span></span>|<span data-ttu-id="04e58-291">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-291">Int32</span></span>|  
|<span data-ttu-id="04e58-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="04e58-292">NULLS</span></span>|<span data-ttu-id="04e58-293">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-293">Int32</span></span>|  
|<span data-ttu-id="04e58-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="04e58-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="04e58-295">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-295">Boolean</span></span>|  
|<span data-ttu-id="04e58-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="04e58-296">AUTO_UPDATE</span></span>|<span data-ttu-id="04e58-297">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-297">Boolean</span></span>|  
|<span data-ttu-id="04e58-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="04e58-298">NULL_COLLATION</span></span>|<span data-ttu-id="04e58-299">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-299">Int32</span></span>|  
|<span data-ttu-id="04e58-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="04e58-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="04e58-301">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-301">Int64</span></span>|  
|<span data-ttu-id="04e58-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-302">COLUMN_NAME</span></span>|<span data-ttu-id="04e58-303">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-303">String</span></span>|  
|<span data-ttu-id="04e58-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-304">COLUMN_GUID</span></span>|<span data-ttu-id="04e58-305">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-305">Guid</span></span>|  
|<span data-ttu-id="04e58-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="04e58-306">COLUMN_PROPID</span></span>|<span data-ttu-id="04e58-307">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-307">Int64</span></span>|  
|<span data-ttu-id="04e58-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="04e58-308">COLLATION</span></span>|<span data-ttu-id="04e58-309">Int16</span><span class="sxs-lookup"><span data-stu-id="04e58-309">Int16</span></span>|  
|<span data-ttu-id="04e58-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="04e58-310">CARDINALITY</span></span>|<span data-ttu-id="04e58-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="04e58-311">Decimal</span></span>|  
|<span data-ttu-id="04e58-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="04e58-312">PAGES</span></span>|<span data-ttu-id="04e58-313">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-313">Int32</span></span>|  
|<span data-ttu-id="04e58-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="04e58-314">FILTER_CONDITION</span></span>|<span data-ttu-id="04e58-315">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-315">String</span></span>|  
|<span data-ttu-id="04e58-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="04e58-316">INTEGRATED</span></span>|<span data-ttu-id="04e58-317">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="04e58-318">Microsoft Oracle-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="04e58-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="04e58-319">Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="04e58-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="04e58-320">Tabellen</span><span class="sxs-lookup"><span data-stu-id="04e58-320">Tables</span></span>  
  
- <span data-ttu-id="04e58-321">Spalten</span><span class="sxs-lookup"><span data-stu-id="04e58-321">Columns</span></span>  
  
- <span data-ttu-id="04e58-322">Verfahren</span><span class="sxs-lookup"><span data-stu-id="04e58-322">Procedures</span></span>  
  
- <span data-ttu-id="04e58-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="04e58-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="04e58-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="04e58-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="04e58-325">Ansichten</span><span class="sxs-lookup"><span data-stu-id="04e58-325">Views</span></span>  
  
- <span data-ttu-id="04e58-326">Indizes</span><span class="sxs-lookup"><span data-stu-id="04e58-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="04e58-327">Tabellen</span><span class="sxs-lookup"><span data-stu-id="04e58-327">Tables</span></span>  
  
|<span data-ttu-id="04e58-328">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-328">ColumnName</span></span>|<span data-ttu-id="04e58-329">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-330">TABLE_CATALOG</span></span>|<span data-ttu-id="04e58-331">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-331">String</span></span>|  
|<span data-ttu-id="04e58-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="04e58-333">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-333">String</span></span>|  
|<span data-ttu-id="04e58-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-334">TABLE_NAME</span></span>|<span data-ttu-id="04e58-335">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-335">String</span></span>|  
|<span data-ttu-id="04e58-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-336">TABLE_TYPE</span></span>|<span data-ttu-id="04e58-337">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-337">String</span></span>|  
|<span data-ttu-id="04e58-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-338">TABLE_GUID</span></span>|<span data-ttu-id="04e58-339">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-339">Guid</span></span>|  
|<span data-ttu-id="04e58-340">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-340">DESCRIPTION</span></span>|<span data-ttu-id="04e58-341">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-341">String</span></span>|  
|<span data-ttu-id="04e58-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="04e58-342">TABLE_PROPID</span></span>|<span data-ttu-id="04e58-343">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-343">Int64</span></span>|  
|<span data-ttu-id="04e58-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="04e58-344">DATE_CREATED</span></span>|<span data-ttu-id="04e58-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-345">DateTime</span></span>|  
|<span data-ttu-id="04e58-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="04e58-346">DATE_MODIFIED</span></span>|<span data-ttu-id="04e58-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="04e58-348">Spalten</span><span class="sxs-lookup"><span data-stu-id="04e58-348">Columns</span></span>  
  
|<span data-ttu-id="04e58-349">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-349">ColumnName</span></span>|<span data-ttu-id="04e58-350">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-351">TABLE_CATALOG</span></span>|<span data-ttu-id="04e58-352">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-352">String</span></span>|  
|<span data-ttu-id="04e58-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="04e58-354">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-354">String</span></span>|  
|<span data-ttu-id="04e58-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-355">TABLE_NAME</span></span>|<span data-ttu-id="04e58-356">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-356">String</span></span>|  
|<span data-ttu-id="04e58-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-357">COLUMN_NAME</span></span>|<span data-ttu-id="04e58-358">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-358">String</span></span>|  
|<span data-ttu-id="04e58-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-359">COLUMN_GUID</span></span>|<span data-ttu-id="04e58-360">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-360">Guid</span></span>|  
|<span data-ttu-id="04e58-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="04e58-361">COLUMN_PROPID</span></span>|<span data-ttu-id="04e58-362">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-362">Int64</span></span>|  
|<span data-ttu-id="04e58-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="04e58-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="04e58-364">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-364">Int64</span></span>|  
|<span data-ttu-id="04e58-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="04e58-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="04e58-366">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-366">Boolean</span></span>|  
|<span data-ttu-id="04e58-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="04e58-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="04e58-368">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-368">String</span></span>|  
|<span data-ttu-id="04e58-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="04e58-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="04e58-370">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-370">Int64</span></span>|  
|<span data-ttu-id="04e58-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="04e58-371">IS_NULLABLE</span></span>|<span data-ttu-id="04e58-372">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-372">Boolean</span></span>|  
|<span data-ttu-id="04e58-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-373">DATA_TYPE</span></span>|<span data-ttu-id="04e58-374">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-374">Int32</span></span>|  
|<span data-ttu-id="04e58-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-375">TYPE_GUID</span></span>|<span data-ttu-id="04e58-376">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-376">Guid</span></span>|  
|<span data-ttu-id="04e58-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="04e58-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="04e58-378">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-378">Int64</span></span>|  
|<span data-ttu-id="04e58-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="04e58-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="04e58-380">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-380">Int64</span></span>|  
|<span data-ttu-id="04e58-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="04e58-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="04e58-382">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-382">Int32</span></span>|  
|<span data-ttu-id="04e58-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="04e58-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="04e58-384">Int16</span><span class="sxs-lookup"><span data-stu-id="04e58-384">Int16</span></span>|  
|<span data-ttu-id="04e58-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="04e58-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="04e58-386">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-386">Int64</span></span>|  
|<span data-ttu-id="04e58-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="04e58-388">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-388">String</span></span>|  
|<span data-ttu-id="04e58-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="04e58-390">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-390">String</span></span>|  
|<span data-ttu-id="04e58-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="04e58-392">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-392">String</span></span>|  
|<span data-ttu-id="04e58-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="04e58-394">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-394">String</span></span>|  
|<span data-ttu-id="04e58-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="04e58-396">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-396">String</span></span>|  
|<span data-ttu-id="04e58-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-397">COLLATION_NAME</span></span>|<span data-ttu-id="04e58-398">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-398">String</span></span>|  
|<span data-ttu-id="04e58-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="04e58-400">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-400">String</span></span>|  
|<span data-ttu-id="04e58-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="04e58-402">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-402">String</span></span>|  
|<span data-ttu-id="04e58-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-403">DOMAIN_NAME</span></span>|<span data-ttu-id="04e58-404">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-404">String</span></span>|  
|<span data-ttu-id="04e58-405">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-405">DESCRIPTION</span></span>|<span data-ttu-id="04e58-406">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="04e58-407">Verfahren</span><span class="sxs-lookup"><span data-stu-id="04e58-407">Procedures</span></span>  
  
|<span data-ttu-id="04e58-408">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-408">ColumnName</span></span>|<span data-ttu-id="04e58-409">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="04e58-411">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-411">String</span></span>|  
|<span data-ttu-id="04e58-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="04e58-413">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-413">String</span></span>|  
|<span data-ttu-id="04e58-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="04e58-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-415">String</span></span>|  
|<span data-ttu-id="04e58-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="04e58-417">Int16</span><span class="sxs-lookup"><span data-stu-id="04e58-417">Int16</span></span>|  
|<span data-ttu-id="04e58-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="04e58-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="04e58-419">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-419">String</span></span>|  
|<span data-ttu-id="04e58-420">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-420">DESCRIPTION</span></span>|<span data-ttu-id="04e58-421">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-421">String</span></span>|  
|<span data-ttu-id="04e58-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="04e58-422">DATE_CREATED</span></span>|<span data-ttu-id="04e58-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-423">DateTime</span></span>|  
|<span data-ttu-id="04e58-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="04e58-424">DATE_MODIFIED</span></span>|<span data-ttu-id="04e58-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="04e58-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="04e58-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="04e58-427">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-427">ColumnName</span></span>|<span data-ttu-id="04e58-428">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="04e58-430">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-430">String</span></span>|  
|<span data-ttu-id="04e58-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="04e58-432">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-432">String</span></span>|  
|<span data-ttu-id="04e58-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="04e58-434">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-434">String</span></span>|  
|<span data-ttu-id="04e58-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-435">COLUMN_NAME</span></span>|<span data-ttu-id="04e58-436">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-436">String</span></span>|  
|<span data-ttu-id="04e58-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-437">COLUMN_GUID</span></span>|<span data-ttu-id="04e58-438">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-438">Guid</span></span>|  
|<span data-ttu-id="04e58-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="04e58-439">COLUMN_PROPID</span></span>|<span data-ttu-id="04e58-440">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-440">Int64</span></span>|  
|<span data-ttu-id="04e58-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="04e58-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="04e58-442">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-442">Int64</span></span>|  
|<span data-ttu-id="04e58-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="04e58-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="04e58-444">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-444">Int64</span></span>|  
|<span data-ttu-id="04e58-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="04e58-445">IS_NULLABLE</span></span>|<span data-ttu-id="04e58-446">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-446">Boolean</span></span>|  
|<span data-ttu-id="04e58-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-447">DATA_TYPE</span></span>|<span data-ttu-id="04e58-448">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-448">Int32</span></span>|  
|<span data-ttu-id="04e58-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-449">TYPE_GUID</span></span>|<span data-ttu-id="04e58-450">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-450">Guid</span></span>|  
|<span data-ttu-id="04e58-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="04e58-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="04e58-452">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-452">Int64</span></span>|  
|<span data-ttu-id="04e58-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="04e58-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="04e58-454">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-454">Int64</span></span>|  
|<span data-ttu-id="04e58-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="04e58-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="04e58-456">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-456">Int32</span></span>|  
|<span data-ttu-id="04e58-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="04e58-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="04e58-458">Int16</span><span class="sxs-lookup"><span data-stu-id="04e58-458">Int16</span></span>|  
|<span data-ttu-id="04e58-459">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-459">DESCRIPTION</span></span>|<span data-ttu-id="04e58-460">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-460">String</span></span>|  
|<span data-ttu-id="04e58-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="04e58-461">OVERLOAD</span></span>|<span data-ttu-id="04e58-462">Int16</span><span class="sxs-lookup"><span data-stu-id="04e58-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="04e58-463">Ansichten</span><span class="sxs-lookup"><span data-stu-id="04e58-463">Views</span></span>  
  
|<span data-ttu-id="04e58-464">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-464">ColumnName</span></span>|<span data-ttu-id="04e58-465">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-466">TABLE_CATALOG</span></span>|<span data-ttu-id="04e58-467">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-467">String</span></span>|  
|<span data-ttu-id="04e58-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="04e58-469">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-469">String</span></span>|  
|<span data-ttu-id="04e58-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-470">TABLE_NAME</span></span>|<span data-ttu-id="04e58-471">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-471">String</span></span>|  
|<span data-ttu-id="04e58-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="04e58-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="04e58-473">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-473">String</span></span>|  
|<span data-ttu-id="04e58-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="04e58-474">CHECK_OPTION</span></span>|<span data-ttu-id="04e58-475">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-475">Boolean</span></span>|  
|<span data-ttu-id="04e58-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="04e58-476">IS_UPDATABLE</span></span>|<span data-ttu-id="04e58-477">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-477">Boolean</span></span>|  
|<span data-ttu-id="04e58-478">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-478">DESCRIPTION</span></span>|<span data-ttu-id="04e58-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-479">String</span></span>|  
|<span data-ttu-id="04e58-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="04e58-480">DATE_CREATED</span></span>|<span data-ttu-id="04e58-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-481">DateTime</span></span>|  
|<span data-ttu-id="04e58-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="04e58-482">DATE_MODIFIED</span></span>|<span data-ttu-id="04e58-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="04e58-484">Indizes</span><span class="sxs-lookup"><span data-stu-id="04e58-484">Indexes</span></span>  
  
|<span data-ttu-id="04e58-485">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-485">ColumnName</span></span>|<span data-ttu-id="04e58-486">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-487">TABLE_CATALOG</span></span>|<span data-ttu-id="04e58-488">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-488">String</span></span>|  
|<span data-ttu-id="04e58-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="04e58-490">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-490">String</span></span>|  
|<span data-ttu-id="04e58-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-491">TABLE_NAME</span></span>|<span data-ttu-id="04e58-492">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-492">String</span></span>|  
|<span data-ttu-id="04e58-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-493">INDEX_CATALOG</span></span>|<span data-ttu-id="04e58-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-494">String</span></span>|  
|<span data-ttu-id="04e58-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="04e58-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-496">String</span></span>|  
|<span data-ttu-id="04e58-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-497">INDEX_NAME</span></span>|<span data-ttu-id="04e58-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-498">String</span></span>|  
|<span data-ttu-id="04e58-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="04e58-499">PRIMARY_KEY</span></span>|<span data-ttu-id="04e58-500">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-500">Boolean</span></span>|  
|<span data-ttu-id="04e58-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="04e58-501">UNIQUE</span></span>|<span data-ttu-id="04e58-502">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-502">Boolean</span></span>|  
|<span data-ttu-id="04e58-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="04e58-503">CLUSTERED</span></span>|<span data-ttu-id="04e58-504">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-504">Boolean</span></span>|  
|<span data-ttu-id="04e58-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-505">TYPE</span></span>|<span data-ttu-id="04e58-506">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-506">Int32</span></span>|  
|<span data-ttu-id="04e58-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="04e58-507">FILL_FACTOR</span></span>|<span data-ttu-id="04e58-508">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-508">Int32</span></span>|  
|<span data-ttu-id="04e58-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="04e58-509">INITIAL_SIZE</span></span>|<span data-ttu-id="04e58-510">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-510">Int32</span></span>|  
|<span data-ttu-id="04e58-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="04e58-511">NULLS</span></span>|<span data-ttu-id="04e58-512">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-512">Int32</span></span>|  
|<span data-ttu-id="04e58-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="04e58-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="04e58-514">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-514">Boolean</span></span>|  
|<span data-ttu-id="04e58-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="04e58-515">AUTO_UPDATE</span></span>|<span data-ttu-id="04e58-516">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-516">Boolean</span></span>|  
|<span data-ttu-id="04e58-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="04e58-517">NULL_COLLATION</span></span>|<span data-ttu-id="04e58-518">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-518">Int32</span></span>|  
|<span data-ttu-id="04e58-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="04e58-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="04e58-520">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-520">Int64</span></span>|  
|<span data-ttu-id="04e58-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-521">COLUMN_NAME</span></span>|<span data-ttu-id="04e58-522">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-522">String</span></span>|  
|<span data-ttu-id="04e58-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-523">COLUMN_GUID</span></span>|<span data-ttu-id="04e58-524">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-524">Guid</span></span>|  
|<span data-ttu-id="04e58-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="04e58-525">COLUMN_PROPID</span></span>|<span data-ttu-id="04e58-526">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-526">Int64</span></span>|  
|<span data-ttu-id="04e58-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="04e58-527">COLLATION</span></span>|<span data-ttu-id="04e58-528">Int16</span><span class="sxs-lookup"><span data-stu-id="04e58-528">Int16</span></span>|  
|<span data-ttu-id="04e58-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="04e58-529">CARDINALITY</span></span>|<span data-ttu-id="04e58-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="04e58-530">Decimal</span></span>|  
|<span data-ttu-id="04e58-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="04e58-531">PAGES</span></span>|<span data-ttu-id="04e58-532">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-532">Int32</span></span>|  
|<span data-ttu-id="04e58-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="04e58-533">FILTER_CONDITION</span></span>|<span data-ttu-id="04e58-534">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-534">String</span></span>|  
|<span data-ttu-id="04e58-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="04e58-535">INTEGRATED</span></span>|<span data-ttu-id="04e58-536">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="04e58-537">Microsoft Jet OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="04e58-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="04e58-538">Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="04e58-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="04e58-539">Tabellen</span><span class="sxs-lookup"><span data-stu-id="04e58-539">Tables</span></span>  
  
- <span data-ttu-id="04e58-540">Spalten</span><span class="sxs-lookup"><span data-stu-id="04e58-540">Columns</span></span>  
  
- <span data-ttu-id="04e58-541">Verfahren</span><span class="sxs-lookup"><span data-stu-id="04e58-541">Procedures</span></span>  
  
- <span data-ttu-id="04e58-542">Ansichten</span><span class="sxs-lookup"><span data-stu-id="04e58-542">Views</span></span>  
  
- <span data-ttu-id="04e58-543">Indizes</span><span class="sxs-lookup"><span data-stu-id="04e58-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="04e58-544">Tabellen</span><span class="sxs-lookup"><span data-stu-id="04e58-544">Tables</span></span>  
  
|<span data-ttu-id="04e58-545">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-545">ColumnName</span></span>|<span data-ttu-id="04e58-546">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-547">TABLE_CATALOG</span></span>|<span data-ttu-id="04e58-548">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-548">String</span></span>|  
|<span data-ttu-id="04e58-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="04e58-550">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-550">String</span></span>|  
|<span data-ttu-id="04e58-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-551">TABLE_NAME</span></span>|<span data-ttu-id="04e58-552">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-552">String</span></span>|  
|<span data-ttu-id="04e58-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-553">TABLE_TYPE</span></span>|<span data-ttu-id="04e58-554">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-554">String</span></span>|  
|<span data-ttu-id="04e58-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-555">TABLE_GUID</span></span>|<span data-ttu-id="04e58-556">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-556">Guid</span></span>|  
|<span data-ttu-id="04e58-557">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-557">DESCRIPTION</span></span>|<span data-ttu-id="04e58-558">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-558">String</span></span>|  
|<span data-ttu-id="04e58-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="04e58-559">TABLE_PROPID</span></span>|<span data-ttu-id="04e58-560">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-560">Int64</span></span>|  
|<span data-ttu-id="04e58-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="04e58-561">DATE_CREATED</span></span>|<span data-ttu-id="04e58-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-562">DateTime</span></span>|  
|<span data-ttu-id="04e58-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="04e58-563">DATE_MODIFIED</span></span>|<span data-ttu-id="04e58-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="04e58-565">Spalten</span><span class="sxs-lookup"><span data-stu-id="04e58-565">Columns</span></span>  
  
|<span data-ttu-id="04e58-566">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-566">ColumnName</span></span>|<span data-ttu-id="04e58-567">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-568">TABLE_CATALOG</span></span>|<span data-ttu-id="04e58-569">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-569">String</span></span>|  
|<span data-ttu-id="04e58-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="04e58-571">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-571">String</span></span>|  
|<span data-ttu-id="04e58-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-572">TABLE_NAME</span></span>|<span data-ttu-id="04e58-573">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-573">String</span></span>|  
|<span data-ttu-id="04e58-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-574">COLUMN_NAME</span></span>|<span data-ttu-id="04e58-575">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-575">String</span></span>|  
|<span data-ttu-id="04e58-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-576">COLUMN_GUID</span></span>|<span data-ttu-id="04e58-577">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-577">Guid</span></span>|  
|<span data-ttu-id="04e58-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="04e58-578">COLUMN_PROPID</span></span>|<span data-ttu-id="04e58-579">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-579">Int64</span></span>|  
|<span data-ttu-id="04e58-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="04e58-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="04e58-581">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-581">Int64</span></span>|  
|<span data-ttu-id="04e58-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="04e58-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="04e58-583">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-583">Boolean</span></span>|  
|<span data-ttu-id="04e58-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="04e58-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="04e58-585">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-585">String</span></span>|  
|<span data-ttu-id="04e58-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="04e58-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="04e58-587">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-587">Int64</span></span>|  
|<span data-ttu-id="04e58-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="04e58-588">IS_NULLABLE</span></span>|<span data-ttu-id="04e58-589">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-589">Boolean</span></span>|  
|<span data-ttu-id="04e58-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-590">DATA_TYPE</span></span>|<span data-ttu-id="04e58-591">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-591">Int32</span></span>|  
|<span data-ttu-id="04e58-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-592">TYPE_GUID</span></span>|<span data-ttu-id="04e58-593">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-593">Guid</span></span>|  
|<span data-ttu-id="04e58-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="04e58-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="04e58-595">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-595">Int64</span></span>|  
|<span data-ttu-id="04e58-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="04e58-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="04e58-597">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-597">Int64</span></span>|  
|<span data-ttu-id="04e58-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="04e58-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="04e58-599">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-599">Int32</span></span>|  
|<span data-ttu-id="04e58-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="04e58-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="04e58-601">Int16</span><span class="sxs-lookup"><span data-stu-id="04e58-601">Int16</span></span>|  
|<span data-ttu-id="04e58-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="04e58-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="04e58-603">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-603">Int64</span></span>|  
|<span data-ttu-id="04e58-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="04e58-605">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-605">String</span></span>|  
|<span data-ttu-id="04e58-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="04e58-607">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-607">String</span></span>|  
|<span data-ttu-id="04e58-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="04e58-609">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-609">String</span></span>|  
|<span data-ttu-id="04e58-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="04e58-611">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-611">String</span></span>|  
|<span data-ttu-id="04e58-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="04e58-613">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-613">String</span></span>|  
|<span data-ttu-id="04e58-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-614">COLLATION_NAME</span></span>|<span data-ttu-id="04e58-615">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-615">String</span></span>|  
|<span data-ttu-id="04e58-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="04e58-617">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-617">String</span></span>|  
|<span data-ttu-id="04e58-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="04e58-619">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-619">String</span></span>|  
|<span data-ttu-id="04e58-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-620">DOMAIN_NAME</span></span>|<span data-ttu-id="04e58-621">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-621">String</span></span>|  
|<span data-ttu-id="04e58-622">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-622">DESCRIPTION</span></span>|<span data-ttu-id="04e58-623">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="04e58-624">Verfahren</span><span class="sxs-lookup"><span data-stu-id="04e58-624">Procedures</span></span>  
  
|<span data-ttu-id="04e58-625">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-625">ColumnName</span></span>|<span data-ttu-id="04e58-626">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="04e58-628">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-628">String</span></span>|  
|<span data-ttu-id="04e58-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="04e58-630">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-630">String</span></span>|  
|<span data-ttu-id="04e58-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="04e58-632">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-632">String</span></span>|  
|<span data-ttu-id="04e58-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="04e58-634">Int16</span><span class="sxs-lookup"><span data-stu-id="04e58-634">Int16</span></span>|  
|<span data-ttu-id="04e58-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="04e58-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="04e58-636">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-636">String</span></span>|  
|<span data-ttu-id="04e58-637">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-637">DESCRIPTION</span></span>|<span data-ttu-id="04e58-638">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-638">String</span></span>|  
|<span data-ttu-id="04e58-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="04e58-639">DATE_CREATED</span></span>|<span data-ttu-id="04e58-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-640">DateTime</span></span>|  
|<span data-ttu-id="04e58-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="04e58-641">DATE_MODIFIED</span></span>|<span data-ttu-id="04e58-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="04e58-643">Ansichten</span><span class="sxs-lookup"><span data-stu-id="04e58-643">Views</span></span>  
  
|<span data-ttu-id="04e58-644">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-644">ColumnName</span></span>|<span data-ttu-id="04e58-645">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-646">TABLE_CATALOG</span></span>|<span data-ttu-id="04e58-647">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-647">String</span></span>|  
|<span data-ttu-id="04e58-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="04e58-649">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-649">String</span></span>|  
|<span data-ttu-id="04e58-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-650">TABLE_NAME</span></span>|<span data-ttu-id="04e58-651">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-651">String</span></span>|  
|<span data-ttu-id="04e58-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="04e58-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="04e58-653">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-653">String</span></span>|  
|<span data-ttu-id="04e58-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="04e58-654">CHECK_OPTION</span></span>|<span data-ttu-id="04e58-655">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-655">Boolean</span></span>|  
|<span data-ttu-id="04e58-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="04e58-656">IS_UPDATABLE</span></span>|<span data-ttu-id="04e58-657">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-657">Boolean</span></span>|  
|<span data-ttu-id="04e58-658">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="04e58-658">DESCRIPTION</span></span>|<span data-ttu-id="04e58-659">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-659">String</span></span>|  
|<span data-ttu-id="04e58-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="04e58-660">DATE_CREATED</span></span>|<span data-ttu-id="04e58-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-661">DateTime</span></span>|  
|<span data-ttu-id="04e58-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="04e58-662">DATE_MODIFIED</span></span>|<span data-ttu-id="04e58-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="04e58-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="04e58-664">Indizes</span><span class="sxs-lookup"><span data-stu-id="04e58-664">Indexes</span></span>  
  
|<span data-ttu-id="04e58-665">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04e58-665">ColumnName</span></span>|<span data-ttu-id="04e58-666">DataType</span><span class="sxs-lookup"><span data-stu-id="04e58-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="04e58-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-667">TABLE_CATALOG</span></span>|<span data-ttu-id="04e58-668">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-668">String</span></span>|  
|<span data-ttu-id="04e58-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="04e58-670">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-670">String</span></span>|  
|<span data-ttu-id="04e58-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-671">TABLE_NAME</span></span>|<span data-ttu-id="04e58-672">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-672">String</span></span>|  
|<span data-ttu-id="04e58-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="04e58-673">INDEX_CATALOG</span></span>|<span data-ttu-id="04e58-674">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-674">String</span></span>|  
|<span data-ttu-id="04e58-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="04e58-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="04e58-676">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-676">String</span></span>|  
|<span data-ttu-id="04e58-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-677">INDEX_NAME</span></span>|<span data-ttu-id="04e58-678">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-678">String</span></span>|  
|<span data-ttu-id="04e58-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="04e58-679">PRIMARY_KEY</span></span>|<span data-ttu-id="04e58-680">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-680">Boolean</span></span>|  
|<span data-ttu-id="04e58-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="04e58-681">UNIQUE</span></span>|<span data-ttu-id="04e58-682">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-682">Boolean</span></span>|  
|<span data-ttu-id="04e58-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="04e58-683">CLUSTERED</span></span>|<span data-ttu-id="04e58-684">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-684">Boolean</span></span>|  
|<span data-ttu-id="04e58-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="04e58-685">TYPE</span></span>|<span data-ttu-id="04e58-686">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-686">Int32</span></span>|  
|<span data-ttu-id="04e58-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="04e58-687">FILL_FACTOR</span></span>|<span data-ttu-id="04e58-688">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-688">Int32</span></span>|  
|<span data-ttu-id="04e58-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="04e58-689">INITIAL_SIZE</span></span>|<span data-ttu-id="04e58-690">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-690">Int32</span></span>|  
|<span data-ttu-id="04e58-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="04e58-691">NULLS</span></span>|<span data-ttu-id="04e58-692">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-692">Int32</span></span>|  
|<span data-ttu-id="04e58-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="04e58-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="04e58-694">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-694">Boolean</span></span>|  
|<span data-ttu-id="04e58-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="04e58-695">AUTO_UPDATE</span></span>|<span data-ttu-id="04e58-696">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-696">Boolean</span></span>|  
|<span data-ttu-id="04e58-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="04e58-697">NULL_COLLATION</span></span>|<span data-ttu-id="04e58-698">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-698">Int32</span></span>|  
|<span data-ttu-id="04e58-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="04e58-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="04e58-700">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-700">Int64</span></span>|  
|<span data-ttu-id="04e58-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="04e58-701">COLUMN_NAME</span></span>|<span data-ttu-id="04e58-702">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-702">String</span></span>|  
|<span data-ttu-id="04e58-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-703">COLUMN_GUID</span></span>|<span data-ttu-id="04e58-704">GUID</span><span class="sxs-lookup"><span data-stu-id="04e58-704">Guid</span></span>|  
|<span data-ttu-id="04e58-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="04e58-705">COLUMN_PROPID</span></span>|<span data-ttu-id="04e58-706">Int64</span><span class="sxs-lookup"><span data-stu-id="04e58-706">Int64</span></span>|  
|<span data-ttu-id="04e58-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="04e58-707">COLLATION</span></span>|<span data-ttu-id="04e58-708">Int16</span><span class="sxs-lookup"><span data-stu-id="04e58-708">Int16</span></span>|  
|<span data-ttu-id="04e58-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="04e58-709">CARDINALITY</span></span>|<span data-ttu-id="04e58-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="04e58-710">Decimal</span></span>|  
|<span data-ttu-id="04e58-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="04e58-711">PAGES</span></span>|<span data-ttu-id="04e58-712">Int32</span><span class="sxs-lookup"><span data-stu-id="04e58-712">Int32</span></span>|  
|<span data-ttu-id="04e58-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="04e58-713">FILTER_CONDITION</span></span>|<span data-ttu-id="04e58-714">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="04e58-714">String</span></span>|  
|<span data-ttu-id="04e58-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="04e58-715">INTEGRATED</span></span>|<span data-ttu-id="04e58-716">Boolesch</span><span class="sxs-lookup"><span data-stu-id="04e58-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04e58-717">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04e58-717">See also</span></span>

- [<span data-ttu-id="04e58-718">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="04e58-718">ADO.NET Overview</span></span>](ado-net-overview.md)
