# ホログラム 101

このチュートリアルでは、Unity を使ってビルドするプロジェクト全体について順を追って説明します。このプロジェクトでは、[*視線*](https://developer.microsoft.com/ja-jp/windows/holographic/gaze)、[*ジェスチャー*](https://developer.microsoft.com/ja-jp/windows/holographic/gestures)、[*音声入力*](https://developer.microsoft.com/ja-jp/windows/holographic/voice_input)、[*空間音響*](https://developer.microsoft.com/ja-jp/windows/holographic/spatial_sound)、[*空間マッピング*](https://developer.microsoft.com/ja-jp/windows/holographic/spatial_mapping)など、Windows Holographic Platform と HoloLens の核となる機能を示します。

このチュートリアルの所要時間は約 1 時間です。

## 前提条件

-   [*適切なツールをインストール*](https://developer.microsoft.com/ja-jp/windows/holographic/install_the_tools)して構成した
    Windows 10 PC。
-   [*開発用に構成した*](https://developer.microsoft.com/ja-jp/windows/holographic/Using_Visual_Studio.html#enabling_developer_mode)
    HoloLens デバイス。

## プロジェクト ファイル

-   プロジェクトに必要な[*ファイル*](https://github.com/Microsoft/HolographicAcademy/archive/Holograms-101.zip)はダウンロードします。Unity
    5.5 が必要です。
    -   依然として Unity 5.4 のサポートが必要な場合は、[*こちらのリリース*](https://github.com/Microsoft/HolographicAcademy/archive/v1.5.4-101.zip)を使用してください。
-   デスクトップなどのアクセスしやすい場所にファイルを解凍します。フォルダー名はそのまま Origami を使用します。

## チュートリアルの内容

- [第 1 章 -「ホログラム」の世界](holograms_101.md#第-1-章---ホログラムの世界)
- [第 2 章 – 視線](holograms_101.md#第-2-章--視線)
- [第 3 章 – ジェスチャー](holograms_101.md#第-3-章--ジェスチャー)
- [第 4 章 – 音声](holograms_101.md#第-4-章--音声)
- [第 5 章 – 空間音響](holograms_101.md#第-5-章--空間音響)
- [第 6 章 – 空間マッピング](holograms_101.md#第-6-章--空間マッピング)
- [第 7 章 – ホログラフィックを楽しむ](holograms_101.md#第-7-章--ホログラフィックを楽しむ)
- [終わりに](holograms_101.md#終わりに)

## 第 1 章 - 「ホログラム」の世界

この章では、このチュートリアル最初の Unity
プロジェクトをセットアップし、ビルドと配置のプロセスについて順を追って説明します。

### 目標

-   ホログラフィック開発向けに Unity をセットアップする。
-   ホログラムを作成する。
-   作成したホログラムを確認する。

### 手順

-   Unity を起動します。
-   \[Open\]を選びます。
-   最初にファイルを解凍した Origami フォルダーの場所を入力します。
-   \[Origami\] を選び、\[Select Folder\] をクリックします。
-   Origami プロジェクトにはシーンが含まれていません。そのため、\[File\] の \[Save Scene As\] を使って既定の空のシーンを新しいファイルに保存します。
-   新しいシーンに「Origami」という名前を付けて、\[Save\] をクリックします。

### メイン仮想カメラのセットアップ

-   \[Hierarchy\] パネルで \[Main Camera\] を選びます。
-   \[Inspector\] パネルの \[Transform\] コンポーネントで \[Position\] を (**x**:0, **y**:0, **z**:0)に設定します。
-   \[Clear Flags\] プロパティの一覧で \[Skybox\] を \[Solid color\] に変更します。
-   \[Background\] フィールドをクリックして色の選択ツールを開きます。
-   \[R\]、\[G\]、\[B\] および \[A\] の各フィールドに 0 を設定します。

### シーンのセットアップ

-   \[Hierarchy\] パネルで、\[Create\] 、\[Create Empty\] の順にクリックします。
-   新しく作成された GameObject を右クリックして、\[Rename\] を選びます。GameObjectの名前を「OrigamiCollection」に変更します。
-   \[Project\] パネルで \[Holograms\]フォルダーから以下の操作を行います (\[Assets\] を展開して\[Holograms\] を選ぶか、\[Project\] パネルで\[Holograms\] フォルダーをダブルクリックします)。
    -   OrigamiCollection の子になるように、Stage を \[Hierarchy\] パネルにドラッグします。
    -   OrigamiCollection の子になるように、Sphere1 を \[Hierarchy\] パネルにドラッグします。
    -   OrigamiCollection の子になるように、Sphere2 を \[Hierarchy\] パネルにドラッグします。
-   \[Hierarchy\] パネルで Directional Lightオブジェクトを右クリックし、\[Delete\] を選びます。
-   \[Holograms\] フォルダーから Lights を \[Hierarchy\] パネルのルートにドラッグします。
-   \[Hierarchy\] パネルで OrigamiCollection を選びます。
-   \[Inspector\] パネルの \[Transform\] コンポーネントで \[Position\] を (**x**:0, **y**:-0.5,**z**:2.0) に設定します。
-   Unity で \[Play\] をクリックしてホログラムをプレビューします。
-   プレビュー ウィンドウに Origami オブジェクトが表示されます。
-   再度 \[Play\] をクリックすると、プレビューモードが停止します。

### Unity から Visual Studio へのプロジェクトのエクスポート

-   Unity で、\[File\] 、\[Build Settings\] の順に選びます。
-   \[Platform\] の一覧で \[Windows Store\] を選び、\[Switch Platform\] をクリックします。
-   \[SDK\] を \[Universal 10\] に、\[Build Type\] を\[D3D\] に設定します。
-   \[Unity C\# Projects\] チェックボックスをオンにします。
-   \[Add Open Scenes\] をクリックして、シーンを追加します。
-   \[Build\] をクリックします。
-   表示されるファイル エクスプローラー ウィンドウで、\[New Folder\] をクリックし、フォルダーに「App」という名前を付けます。
-   \[App\] フォルダーをシングル クリックします。
-   \[Select Folder\] をクリックします。
-   Unity を終了すると、エクスプローラー ウィンドウが表示されます。
-   App フォルダーを開きます。
-   Origami.sln を 開きます。
-   Visual Studio 上部のツール バーを使って、ターゲットを \[Debug\] から\[Release\]、\[ARM\] から \[X86\] に変更します。
-   \[デバイス\] ボタンの横にある矢印をクリックして、\[リモートデバイス\] を選びます。
    -   \[アドレス\] をお使いの HoloLens の名前または IPアドレスに設定します。デバイスの IPアドレスがわからない場合は、\[設定\]、\[ネットワークとインターネット\]、\[詳細オプション\]の順にクリックして IP アドレスを確認するか、Cortana に「私の IPアドレスを教えて」と質問します。
    -   \[認証モード\] は \[ユニバーサル\] のままにします。
    -   \[選択\] をクリックします。
-   \[デバッグ\]、\[デバッグなしで開始\] の順に選ぶか、**Ctrl**キーを押しながら **F5**キーを押します。デバイスに初めて配置する場合は、[*Visual Studioとのペアリング*](https://developer.microsoft.com/ja-jp/windows/holographic/Using_Visual_Studio.html#pairing_your_device)が必要です。
-   ここで、Origami プロジェクトをビルドし、HoloLensに配置して実行します。
-   HoloLens を着用して、あたりを見回し、新しいホログラムを確認します。

## 第 2 章 – 視線

この章では、ホログラムを操作する 3 つの方法のうちの最初の １
つ、[*視線*](https://developer.microsoft.com/ja-jp/windows/holographic/gaze)について説明します。

### 目標

-   世界を固定するカーソルを使って視線を視覚化する。

### 手順

-   Unity プロジェクトに戻ります。\[Build Settings\] ウィンドウが開いたままの場合はこれを閉じます。
-   \[Project\] パネルで \[Holograms\]フォルダーを選びます。
-   Cursor オブジェクトを \[Hierarchy\] パネルのルートレベルにドラッグします。
-   Cursorオブジェクトをダブルクリックして、このオブジェクトを詳しく調べます。
-   \[Project\] パネルで \[Scripts\]フォルダーを右クリックします。
-   \[Create\] サブメニューをクリックします。
-   \[C\# Script\] を選びます。
-   スクリプトの名前を「WorldCursor」にします。メモ:名前は、大文字と小文字が区別されます。拡張子 .csを追加する必要はありません。
-   \[Hierarchy\] パネルで Cursor オブジェクトを選びます。
-   WorldCursor スクリプトをドラッグして、\[Inspector\] パネルにドロップします。
-   WorldCursor スクリプトをダブルクリックして Visual Studioで開きます。
-   次のコードをコピーして WorldCursor.cs に貼り付け、\[すべて保存\]をクリックします。

WorldCursor.cs
```cs
using UnityEngine;

public class WorldCursor : MonoBehaviour
{
    private MeshRenderer meshRenderer;

    // Use this for initialization
    void Start()
    {
        // Grab the mesh renderer that&#39;s on the same object as this script.
        meshRenderer = this.gameObject.GetComponentInChildren&lt;MeshRenderer&gt;();
    }

    // Update is called once per frame
    void Update()
    {
        // Do a raycast into the world based on the user&#39;s
        // head position and orientation.
        var headPosition = Camera.main.transform.position;
        var gazeDirection = Camera.main.transform.forward;

        RaycastHit hitInfo;

        if (Physics.Raycast(headPosition, gazeDirection, out hitInfo))
        {
            // If the raycast hit a hologram...
            // Display the cursor mesh.
            meshRenderer.enabled = true;

            // Move the cursor to the point where the raycast hit.
            this.transform.position = hitInfo.point;

            // Rotate the cursor to hug the surface of the hologram.
            this.transform.rotation = Quaternion.FromToRotation(Vector3.up, hitInfo.normal);
        }
        else
        {
            // If the raycast did not hit a hologram, hide the cursor mesh.
            meshRenderer.enabled = false;
        }
    }
}
```

-   \[File\] 、\[Build Settings\] の順に選んで、アプリをリビルドします。
-   前回 HoloLens の配置に使用した Visual Studioソリューションに戻ります。
-   確認が表示される場合には、\[再読み込み\] を選びます。
-   \[デバッグ\]、\[デバッグなしで開始\] の順に選ぶか、**Ctrl**キーを押しながら **F5** キーを押します。
-   ここで、シーンを見回すと、カーソルが物体の形状にどのように関わるかがわかります。

## 第 3 章 – ジェスチャー

この章では、[*ジェスチャー*](https://developer.microsoft.com/ja-jp/windows/holographic/gestures)のサポートを追加します。ここでは紙で作った球体をユーザーが選ぶと、その球体が落ちるようにします。そのため、Unityの物理エンジンを使って重力を有効にします。

### 目標

-   「選ぶ」というジェスチャーを使ってホログラムを制御する。

### 手順

ここでは、最初にスクリプトを作成してから、「選ぶ」というジェスチャーを検出できるようにします。

-   \[Scripts\] フォルダーで、GazeGestureManagerというスクリプトを作成します。
-   GazeGestureManager スクリプトを \[Hierarchy\] パネルのOrigamiCollection オブジェクトにドラッグします。
-   Visual Studio で GazeGestureManagerスクリプトを開き、次のコードを追加します。

GazeGestureManager.cs 
```cs
using UnityEngine;
using UnityEngine.VR.WSA.Input;

public class GazeGestureManager : MonoBehaviour
{
    public static GazeGestureManager Instance { get; private set; }

    // Represents the hologram that is currently being gazed at.
    public GameObject FocusedObject { get; private set; }

    GestureRecognizer recognizer;

    // Use this for initialization
    void Awake()
    {
        Instance = this;

        // Set up a GestureRecognizer to detect Select gestures.
        recognizer = new GestureRecognizer();
        recognizer.TappedEvent += (source, tapCount, ray) =&gt;
        {
            // Send an OnSelect message to the focused object and its ancestors.
            if (FocusedObject != null)
            {
                FocusedObject.SendMessageUpwards(&quot;OnSelect&quot;);
            }
        };
        recognizer.StartCapturingGestures();
    }

    // Update is called once per frame
    void Update()
    {
        // Figure out which hologram is focused this frame.
        GameObject oldFocusObject = FocusedObject;

        // Do a raycast into the world based on the user&#39;s
        // head position and orientation.
        var headPosition = Camera.main.transform.position;
        var gazeDirection = Camera.main.transform.forward;

        RaycastHit hitInfo;
        if (Physics.Raycast(headPosition, gazeDirection, out hitInfo))
        {
            // If the raycast hit a hologram, use that as the focused object.
            FocusedObject = hitInfo.collider.gameObject;
        }
        else
        {
            // If the raycast did not hit a hologram, clear the focused object.
            FocusedObject = null;
        }

        // If the focused object changed this frame,
        // start detecting fresh gestures again.
        if (FocusedObject != oldFocusObject)
        {
            recognizer.CancelGestures();
            recognizer.StartCapturingGestures();
        }
    }
}
```

-   \[Scripts\] フォルダーでもう 1つスクリプトを作成し、今回は「SphereCommands」という名前を付けます。
-   \[Hierarchy\] ビューの OrigamiCollectionオブジェクトを展開します。
-   SphereCommands スクリプトを \[Hierarchy\] パネルの Sphere1オブジェクトにドラッグします。
-   SphereCommands スクリプトを \[Hierarchy\] パネルの Sphere2オブジェクトにドラッグします。
-   編集のために Visual Studioでスクリプトを開き、スクリプト既定のコードを次のコードに置き換えます。

SphereCommands.cs 
```cs
using UnityEngine;

public class SphereCommands : MonoBehaviour
{
    // Called by GazeGestureManager when the user performs a Select gesture
    void OnSelect()
    {
        // If the sphere has no Rigidbody component, add one to enable physics.
        if (!this.GetComponent&lt;Rigidbody&gt;())
        {
            var rigidbody = this.gameObject.AddComponent&lt;Rigidbody&gt;();
            rigidbody.collisionDetectionMode = CollisionDetectionMode.Continuous;
        }
    }
}
```

-   アプリをエクスポートしてビルドし、HoloLens に配置します。
-   球体の １ つを見ます。
-   「選ぶ」ジェスチャーを行い、球体が下の面に落ちるようすを見守ります。

### 第 4 章 – 音声

この章では、2つの[*音声コマンド*](https://developer.microsoft.com/ja-jp/windows/holographic/voice_input)のサポートを追加します。「Reset world」 で落ちた球体を元の場所に戻し、「Drop sphere」 で球体を落下させます。

### 目標

-   常にバックグラウンドで聞こえる音声コマンドを追加する。
-   音声コマンドに反応するホログラムを作成する。

### 手順

-   \[Scripts\] フォルダーで、SpeechManagerというスクリプトを作成します。
-   \[Hierarchy\] パネルの OrigamiCollection オブジェクトにSpeechManager スクリプトをドラッグします。
-   Visual Studio で SpeechManager スクリプトを開きます。
-   次のコードをコピーして SpeechManager.cs に貼り付け、\[すべて保存\]をクリックします。

SpeechManager.cs 
```cs
using System.Collections.Generic;
using System.Linq;
using UnityEngine;
using UnityEngine.Windows.Speech;

public class SpeechManager : MonoBehaviour
{
    KeywordRecognizer keywordRecognizer = null;
    Dictionary&lt;string, System.Action&gt; keywords = new Dictionary&lt;string, System.Action&gt;();

    // Use this for initialization
    void Start()
    {
        keywords.Add(&quot;Reset world&quot;, () =&gt;
        {
            // Call the OnReset method on every descendant object.
            this.BroadcastMessage(&quot;OnReset&quot;);
        });

        keywords.Add(&quot;Drop Sphere&quot;, () =&gt;
        {
            var focusObject = GazeGestureManager.Instance.FocusedObject;
            if (focusObject != null)
            {
                // Call the OnDrop method on just the focused object.
                focusObject.SendMessage(&quot;OnDrop&quot;);
            }
        });

        // Tell the KeywordRecognizer about our keywords.
        keywordRecognizer = new KeywordRecognizer(keywords.Keys.ToArray());

        // Register a callback for the KeywordRecognizer and start recognizing!
        keywordRecognizer.OnPhraseRecognized += KeywordRecognizer_OnPhraseRecognized;
        keywordRecognizer.Start();
    }

    private void KeywordRecognizer_OnPhraseRecognized(PhraseRecognizedEventArgs args)
    {
        System.Action keywordAction;
        if (keywords.TryGetValue(args.text, out keywordAction))
        {
            keywordAction.Invoke();
        }
    }
}
```

-   Visual Studio で SphereCommands スクリプトを開きます。
-   このスクリプトを次のように更新します。

SphereCommands.cs
```cs
using UnityEngine;

public class SphereCommands : MonoBehaviour
{
    Vector3 originalPosition;

    // Use this for initialization
    void Start()
    {
        // Grab the original local position of the sphere when the app starts.
        originalPosition = this.transform.localPosition;
    }

    // Called by GazeGestureManager when the user performs a Select gesture
    void OnSelect()
    {
        // If the sphere has no Rigidbody component, add one to enable physics.
        if (!this.GetComponent&lt;Rigidbody&gt;())
        {
            var rigidbody = this.gameObject.AddComponent&lt;Rigidbody&gt;();
            rigidbody.collisionDetectionMode = CollisionDetectionMode.Continuous;
        }
    }

    // Called by SpeechManager when the user says the &quot;Reset world&quot; command
    void OnReset()
    {
        // If the sphere has a Rigidbody component, remove it to disable physics.
        var rigidbody = this.GetComponent&lt;Rigidbody&gt;();
        if (rigidbody != null)
        {
            DestroyImmediate(rigidbody);
        }

        // Put the sphere back into its original local position.
        this.transform.localPosition = originalPosition;
    }

    // Called by SpeechManager when the user says the &quot;Drop sphere&quot; command
    void OnDrop()
    {
        // Just do the same logic as a Select gesture.
        OnSelect();
    }
}
```

-   アプリをエクスポートしてビルドし、HoloLens に配置します。
-   球体の １ つを見て、「Drop Sphere」 と発話します。
-   「Reset World」 と発話し、球体を元の位置に戻します。

## 第 5 章 – 空間音響

この章では、アプリに音楽を追加してから、特定の動作で音響効果が引き起こされるようにします。ここでは[*空間音響*](https://developer.microsoft.com/ja-jp/windows/holographic/spatial_sound)を使用して、3D空間の特定の場所に効果音を設定します。

### 目標

-   仮想の世界でホログラムを聞く。

### 手順

-   Unity 上部のメニューで \[Edit\] 、\[Project Settings\] 、\[Audio\] の順に選びます。
-   右側の \[Inspector\] パネルで、\[SpatializerPlugin\] の設定で \[MS HRTFSpatializer\] を選びます。
-   \[Project\] パネルの \[Holograms\] フォルダーからAmbience オブジェクトを \[Hierarchy\] パネルのOrigamiCollection オブジェクトにドラッグします。
-   OrigamiCollection を選び、\[Inspector\] パネルの\[Audio Source\] に移動します。以下のプロパティを変更します。
    -   \[Spatialize\] プロパティのチェック ボックスをオンにします。
    -   \[Play On Awake\] をチェック ボックスをオンにします。
    -   スライダーを右端までドラッグして、\[Spatial Blend\] を \[3D\] に変更します。スライドを動かすと、値が0 から 1 の間で変化します。
    -   \[Loop\] プロパティのチェック ボックスをオンにします。
    -   \[3D Sound Settings\] を展開して、\[Doppler Level\] に「0.1」を入力します。
    -   \[Volume Rolloff\] を \[Logarithmic Rolloff\]に設定します。
    -   \[Max Distance\] に「20」を設定します。
-   \[Scripts\] フォルダーで、SphereSounds というスクリプトを作成します。
-   SphereSounds をドラッグして、\[Hierarchy\] パネルの Sphere1 オブジェクトとSphere2 オブジェクトにドロップします。
-   Visual Studio で SphereSounds を開き、次のようにコードを更新して \[すべて保存\] をクリックします。

SphereSounds.cs 
```cs
using UnityEngine;

public class SphereSounds : MonoBehaviour
{
    AudioSource audioSource = null;
    AudioClip impactClip = null;
    AudioClip rollingClip = null;

    bool rolling = false;

    void Start()
    {
        // Add an AudioSource component and set up some defaults
        audioSource = gameObject.AddComponent&lt;AudioSource&gt;();
        audioSource.playOnAwake = false;
        audioSource.spatialize = true;
        audioSource.spatialBlend = 1.0f;
        audioSource.dopplerLevel = 0.0f;
        audioSource.rolloffMode = AudioRolloffMode.Logarithmic;
        audioSource.maxDistance = 20f;

        // Load the Sphere sounds from the Resources folder
        impactClip = Resources.Load&lt;AudioClip&gt;(&quot;Impact&quot;);
        rollingClip = Resources.Load&lt;AudioClip&gt;(&quot;Rolling&quot;);
    }

    // Occurs when this object starts colliding with another object
    void OnCollisionEnter(Collision collision)
    {
        // Play an impact sound if the sphere impacts strongly enough.
        if (collision.relativeVelocity.magnitude &gt;= 0.1f)
        {
            audioSource.clip = impactClip;
            audioSource.Play();
        }
    }

    // Occurs each frame that this object continues to collide with another object
    void OnCollisionStay(Collision collision)
    {
        Rigidbody rigid = this.gameObject.GetComponent&lt;Rigidbody&gt;();

        // Play a rolling sound if the sphere is rolling fast enough.
        if (!rolling &amp;&amp; rigid.velocity.magnitude &gt;= 0.01f)
        {
            rolling = true;
            audioSource.clip = rollingClip;
            audioSource.Play();
        }
        // Stop the rolling sound if rolling slows down.
        else if (rolling &amp;&amp; rigid.velocity.magnitude &lt; 0.01f)
        {
            rolling = false;
            audioSource.Stop();
        }
    }

    // Occurs when this object stops colliding with another object
    void OnCollisionExit(Collision collision)
    {
        // Stop the rolling sound if the object falls off and stops colliding.
        if (rolling)
        {
            rolling = false;
            audioSource.Stop();
        }
    }
}
```

-   スクリプトを保存し、Unity に戻ります。
-   アプリをエクスポートしてビルドし、HoloLens に配置します。
-   ステージに近づいたり、離れたり、左右に動いて音の変化を聞き取ります。

## 第 6 章 – 空間マッピング

ここで、ゲーム
ボードを現実世界の現実の物体に持ち込むために、[*空間マッピング*](https://developer.microsoft.com/ja-jp/windows/holographic/spatial_mapping)を使用します。

### 目標

-   現実世界を仮想世界に持ち込む。
-   最も重要な場所にホログラムを配置する。

### 手順

-   Unity の \[Project\] パネルで \[Holograms\] フォルダーをクリックします。
-   \[Spatial Mapping\] アセットを \[Hierarchy\] パネルのルートにドラッグします。
-   \[Hierarchy\] パネルで Spatial Mapping オブジェクトをクリックします。
-   \[Inspector\] パネルで次のプロパティを変更します。
    -   \[Draw Visual Meshes\] チェック ボックスをオンにします。
    -   \[Draw Material\] に移動して、右側の円をクリックします。上部の検索フィールドに「wireframe」と入力します。結果をクリックしてウィンドウを閉じます。これにより、\[Draw Material\] の値が \[Wireframe\] に変わります。
-   アプリをエクスポートしてビルドし、HoloLens に配置します。
-   アプリを実行すると、ワイヤーフレームのメッシュが現実世界の上に重なります。
-   転がる球体がステージから床に落ちるようすを見守ります。

今度は、OrigamiCollection を新しい場所に移動する方法を示します。

-   \[Scripts\] フォルダーで、TapToPlaceParent というスクリプトを作成します。
-   \[Hierarchy\] パネルの OrigamiCollection を展開し、Stage オブジェクトを選択します。
-   TapToPlaceParent スクリプトを Stage オブジェクトにドラッグします。
-   Visual Studio で TapToPlaceParent スクリプトを開き、次のようにコードを変更します。

TapToPlaceParent.cs 
```cs
using UnityEngine;

public class TapToPlaceParent : MonoBehaviour
{
    bool placing = false;

    // Called by GazeGestureManager when the user performs a Select gesture
    void OnSelect()
    {
        // On each Select gesture, toggle whether the user is in placing mode.
        placing = !placing;

        // If the user is in placing mode, display the spatial mapping mesh.
        if (placing)
        {
            SpatialMapping.Instance.DrawVisualMeshes = true;
        }
        // If the user is not in placing mode, hide the spatial mapping mesh.
        else
        {
            SpatialMapping.Instance.DrawVisualMeshes = false;
        }
    }

    // Update is called once per frame
    void Update()
    {
        // If the user is in placing mode,
        // update the placement to match the user&#39;s gaze.

        if (placing)
        {
            // Do a raycast into the world that will only hit the Spatial Mapping mesh.
            var headPosition = Camera.main.transform.position;
            var gazeDirection = Camera.main.transform.forward;

            RaycastHit hitInfo;
            if (Physics.Raycast(headPosition, gazeDirection, out hitInfo,
                30.0f, SpatialMapping.PhysicsRaycastMask))
            {
                // Move this object&#39;s parent object to
                // where the raycast hit the Spatial Mapping mesh.
                this.transform.parent.position = hitInfo.point;

                // Rotate this object&#39;s parent object to face the user.
                Quaternion toQuat = Camera.main.transform.localRotation;
                toQuat.x = 0;
                toQuat.z = 0;
                this.transform.parent.rotation = toQuat;
            }
        }
    }
}
```

-   アプリをエクスポートしてビルドし、配置します。
-   これで、ゲームに視線を送り、「選ぶ」ジェスチャーを使ってゲームを新しい場所に移動して、再び「選ぶ」ジェスチャーを行うと、ゲームを特定の場所に移動できるようになります。

## 第 7 章 – ホログラフィックを楽しむ

### 目標

-   ホログラフィックの地下の世界への入り口を暴く。

### 手順

ここでは、ホログラフィックの地下の世界を明らかにする方法について説明します。

-   \[Project\] パネルの \[Holograms\] フォルダーで次の操作を行います。
    -   OrigamiCollection の子になるように、Underworld を \[Hierarchy\] パネルにドラッグします。
-   \[Scripts\] フォルダーで HitTarget というスクリプトを作成します。
-   \[Hierarchy\] パネルで OrigamiCollection を展開します。
-   Stage オブジェクトを展開し、Target オブジェクト を選びます。
-   HitTarget スクリプトを Target オブジェクトにドラッグします。
-   Visual Studio で HitTarget スクリプトを開き、次のようにコードを変更します。

HitTarget.cs 
```cs
using UnityEngine;

public class HitTarget : MonoBehaviour
{
    // These public fields become settable properties in the Unity editor.
    public GameObject underworld;
    public GameObject objectToHide;

    // Occurs when this object starts colliding with another object
    void OnCollisionEnter(Collision collision)
    {
        // Hide the stage and show the underworld.
        objectToHide.SetActive(false);
        underworld.SetActive(true);

        // Disable Spatial Mapping to let the spheres enter the underworld.
        SpatialMapping.Instance.MappingEnabled = false;
    }
}
```

-   Unity で、Target オブジェクトを選びます。
-   2 つのパブリック プロパティが Hit Target コンポーネントに表示されるようになります。そこで次のようにして、今回のシーンでオブジェクトを参照する必要があります。
    -   \[Hierarchy\] パネルから Hit Target コンポーネントの \[Underworld\] プロパティに Underworld をドラッグします。
    -   \[Hierarchy\] パネルから Hit Target コンポーネントの \[Object to Hide\] プロパティに Stage をドラッグします。
-   アプリをエクスポートしてビルドし、配置します。
-   Origami Collection を床に置き、「選ぶ」ジェスチャーを使って球体を落とします。
-   球体がターゲット に当たると、爆発が起こります。コレクションは消え去り、地下の世界への穴が現れます。

## 終わりに

これで、このチュートリアルは終わりです。

ここでは以下のことを学びました。

-   Unity でホログラフィック アプリを作成する方法。
-   視線、ジェスチャー、音声、音響、空間マッピングを利用する方法。
-   Visual Studio を使ってアプリをビルドおよび配置する方法。

これで、独自のホログラフィック
エクスペリエンスを生み出す準備が整いました。
