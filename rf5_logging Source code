using UnityEngine;
using Steamworks;
using Il2CppRF5SteamInput;
using System;
using System.Collections.Generic;
using System.Reflection;
using System.Reflection.Emit;
using Il2CppSystem.Reflection;
using HarmonyLib;
using Il2Cpp;
using MelonLoader;
using Il2CppInterop.Runtime.Runtime;
using Il2CppInterop.Runtime.InteropTypes;
using Il2CppInterop.Runtime.XrefScans;
using Il2CppSystem.Runtime.InteropServices;
using Il2CppSRDebugger.UI.Tabs;
using Il2CppDefine;
using UnityEngine.Bindings;
using Il2CppInterop.Runtime;
using static Il2CppSystem.Linq.Expressions.Interpreter.CastInstruction.CastInstructionNoT;
using UnityEngine.Rendering;
using System.Collections;
using Il2CppInterop.Common.XrefScans;
using static MelonLoader.MelonLaunchOptions;

[assembly: MelonInfo(typeof(rf5_logging.Core), "rf5_logging", "1.0.0", "chph", null)]
[assembly: MelonGame("株式会社マーベラス", "Rune Factory 5")]

namespace rf5_logging
{
    public class Core : MelonMod
    {
        public override void OnInitializeMelon()
        {
            //if (SteamAPI.Init())
            //{
            //    MelonLogger.Msg("Steamworks API Initialized!");
            //}
            //else
            //{
            //    MelonLogger.Msg("Failed to initialize Steamworks API!");
            //}
        }

        public override void OnLateInitializeMelon()
        {
            MelonLogger.Msg("Late initialization. 123 ABC");
        }

        public override void OnFixedUpdate()
        {
            //UIMapControl.stayTime = 0f;
        }

        public override void OnUpdate()
        {

            //if (Input.GetKey(KeyCode.O))
            //{
            //    // report the value of UIMapControl.stayTime;
            //    UIMapControl stayTimeReport = GameObject.Find("UIMap(Clone)").GetComponent<UIMapControl>();
            //    MelonLogger.Msg("stayTime is currently: " + stayTimeReport.stayTime);
            //}

            //if (Input.GetKeyDown(KeyCode.Keypad0))
            //{
            //    GameObject playerCharacter = GameObject.Find("PlayerBase");
            //    playerCharacter.transform.position = new Vector3(221.9567f, 19.5119f, 263.2086f);
            //    playerCharacter.transform.rotation = Quaternion.Euler(0, 270, 0);
            //    MelonLogger.Msg("teleported home");

            //    Camera playerCamera = Camera.main;
            //    Transform cameraTransform = playerCamera.transform;
            //    cameraTransform.rotation = Quaternion.Euler(0, 270, 0);
            //}

            //if (Input.GetKeyDown(KeyCode.Keypad1))
            //{
            //    GameObject playerCharacter = GameObject.Find("PlayerBase");
            //    playerCharacter.transform.position = new Vector3(298.8721f, 22.569f, 291.8961f);
            //    playerCharacter.transform.rotation = Quaternion.Euler(0, 270, 0);
            //    MelonLogger.Msg("teleported seed shop");

            //    Camera playerCamera = Camera.main;
            //    Transform cameraTransform = playerCamera.transform;
            //    cameraTransform.rotation = Quaternion.Euler(0, 270, 0);
            //}

            //if (Input.GetKeyDown(KeyCode.Keypad2))
            //{
            //    GameObject playerCharacter = GameObject.Find("PlayerBase");
            //    playerCharacter.transform.position = new Vector3(353.9302f, 20.9036f, 290.2177f);
            //    playerCharacter.transform.rotation = Quaternion.Euler(0, 0, 0);
            //    MelonLogger.Msg("teleported bathhouse");

            //    Camera playerCamera = Camera.main;
            //    Transform cameraTransform = playerCamera.transform;
            //    cameraTransform.rotation = Quaternion.Euler(0, 0, 0);
            //}

            //if (Input.GetKeyDown(KeyCode.KeypadPlus))
            //{
            //    MelonLogger.Msg("Keypad 0 - teleport home");
            //    MelonLogger.Msg("Keypad 1 - teleport seed shop");
            //    MelonLogger.Msg("Keypad 2 - teleport bathhouse");
            //}

            //if (Input.GetKeyDown(KeyCode.Quote))
            //{
            //    Animator animator = GameObject.Find("TeleportAreaManager").GetComponent<UnityEngine.Animator>();

            //    if (animator == null || animator.runtimeAnimatorController == null)
            //    {
            //        MelonLogger.Msg("No Animator or Animator Controller found on this object.");
            //        return;
            //    }

            //    // Get all animations from the Animator Controller
            //    AnimationClip[] clips = animator.runtimeAnimatorController.animationClips;

            //    foreach (AnimationClip clip in clips)
            //    {
            //        MelonLogger.Msg("Animation Name: " + clip.name);
            //    }
            //}

            //if (Input.GetKey(KeyCode.Keypad7))
            //{
            //    GameObject TAM = GameObject.Find("TeleportAreaManager");
            //    TeleportAreaManager TAM_component = TAM.GetComponent<Il2Cpp.TeleportAreaManager>();
            //    bool result = TAM_component.IsTeleporting;
            //    MelonLogger.Msg(result);
            //}

            // man, fast teleport would've been crazy
            // maybe just speed up the animation? float? curve? rate?
        }

        [HarmonyPatch(typeof(UIMapControl), "Update")]
        public static class UIMapControl_Patch_Start
        {
            public static void Postfix()
            {
                //MelonLogger.Msg("ts going off frfr 100 fuck man");
                GameObject warpMenu = GameObject.Find("UIMap(Clone)").transform.Find("WarpMenu").gameObject;
                UIOnOffAnimate warpMenuComponent = warpMenu.GetComponent<UIOnOffAnimate>();
                warpMenuComponent.MoveTime = 0f;

                GameObject warpMenu_Floor = GameObject.Find("UIMap(Clone)").transform.Find("WarpMenu_Floor").gameObject;
                UIOnOffAnimate warpMenu_Floor_Component = warpMenu_Floor.GetComponent<UIOnOffAnimate>();
                warpMenu_Floor_Component.MoveTime = 0f;

                UIMapControl UIMapControl = GameObject.Find("UIMap(Clone)").GetComponent<UIMapControl>();
                UIMapControl.stayTime = 0f;

                MapControl MapControl = GameObject.Find("MapContorol").GetComponent<MapControl>();
                MapControl.infoScrollTime = 0f;

                TwoChoicePopupMain TwoChoicePopupMain = GameObject.Find("UI2ChoicePopup(Clone)").GetComponent<TwoChoicePopupMain>();
                TwoChoicePopupMain.closeTime = 0f;
                TwoChoicePopupMain.closeTimeMax = 0f;
                TwoChoicePopupMain.openTime = 0f;
                TwoChoicePopupMain.openTimeMax = 0f;

                UIOnOffAnimate UIOnOffAnimate_1 = GameObject.Find("WarpMenu").GetComponent<UIOnOffAnimate>();
                UIOnOffAnimate_1.MoveTime = 0f;

                UIOnOffAnimate UIOnOffAnimate_2 = GameObject.Find("WarpMenu_Floor").GetComponent<UIOnOffAnimate>();
                UIOnOffAnimate_2.MoveTime = 0f;
            }
        }
    }
}
