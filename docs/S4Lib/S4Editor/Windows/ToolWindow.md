# Tool Window

```c++

namespace S4Lib
{
	class ToolWindow
	{
		friend class S4Editor;
	public:
		ToolWindow(S4Editor& editor);
		
		void Render();
		
		inline bool IsActive() const;
		inline void SetActive(bool state);
		
		inline void SetTitleAndIcon(const char* title, const char* icon);
		inline void SetTitle(const char* title);
		inline void SetIcon(const char* icon);
		
		inline S4RESULT SaveWindowSettings();
		inline S4RESULT LoadWindowSettings();
	
	protected:
		S4Editor& mEditor;
		bool mIsOpen;
		ImGuiWindowFlags mWindowFlags;
		std::string mWindowTitle;
		
		std::function<S4RESULT()> mUpdateCallbackProc;
		std::function<S4RESULT()> mUpdateCallback;
		std::function<S4RESULT()> mUpdateCallback;
		
	private:
		void UpdateWindowTitle();
		S4RESULT Example();
	};
}```