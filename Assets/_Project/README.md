\# FinalSlice — Unity 3D Project (Module 08)



Проєкт 3D-гри з завершеним ігровим циклом, побудований на базі Unity 6 (Universal 3D) та подійній архітектурі.



\## Інформація про середовище

\* \*\*Версія Unity:\*\* 6000.3.23f1 (або 6000.5.x)

\* \*\*Шаблон:\*\* Universal 3D (URP)

\* \*\*Головні пакети:\*\* Input System, TextMeshPro, Universal RP

\* \*\*Початкова сцена:\*\* `Assets/\_Project/Scenes/FinalSlice.unity` (Build Index 0)



\## Керування у грі

\* \*\*W / A / S / D:\*\* Фізичний рух кулі (Player) у площині XZ.

\* \*\*Кнопка UI (Restart):\*\* Перезапуск поточного раунду сцени.



\## Головний ігровий цикл (Core Loop)

1\. Гравець керує кулею та збирає енергетичні предмети (`SessionPickup`).

2\. При перетині тригера предмет відправляє команду `Collect()` до менеджера `GameSession`.

3\. `GameSession` оновлює рахунок і сповіщає `SessionHud` через подію `Action Changed`.

4\. При досягненні цілі (`PickupsToWin` з `GameRules`) HUD виводить текстове повідомлення про перемогу.

5\. Натискання кнопки \*\*Restart\*\* викликає асинхронне перезавантаження сцени `SceneManager.LoadSceneAsync()`.



\## Схема відповідальностей

\* \*\*`GameRules` (ScriptableObject):\*\* Зберігає глобальні правила та ціль (кількість предметів).

\* \*\*`GameSession` (MonoBehaviour):\*\* Тримає поточний стан раунду (Collected, Won), захищає від повторного рестарту.

\* \*\*`SessionPickup` (MonoBehaviour):\*\* Тригер-сенсор збирання предметів.

\* \*\*`SessionHud` (MonoBehaviour):\*\* Передплатник подій `GameSession`, оновлює вивід TextMeshPro.

\* \*\*`SlicePlayer` (MonoBehaviour):\*\* Зчитує `Keyboard.current` і прискорює `Rigidbody`.



\## Інструкція зі створення та запуску Build

1\. Відкрийте проєкт у Unity Editor.

2\. Перейдіть у \*\*File → Build Profiles\*\*.

3\. Переконайтеся, що сцена `Assets/\_Project/Scenes/FinalSlice.unity` додана під індексом `0`.

4\. Натисніть \*\*Build\*\* та вкажіть цільову папку `Builds/FinalSlice/`.

5\. Запустіть виконуваний файл `FinalSlice.exe`.



\## Відомі обмеження

\* Сцена розрахована на одного гравця.

\* Управління за замовчуванням налаштовано під клавіатуру PC (WASD).

