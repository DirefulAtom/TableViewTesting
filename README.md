# TableViewTesting
Testing table view functionality in Xcode after it broke in another project, to establish if the error is the fault of the software or the developer.

Obviously, the problem was with the developer (me). I was having the same issue from my original project crop up here and I'm not quite sure how I
fixed it, but the original problem was that I was getting a source:key failure with my TableView object. Writing and setting up the view from scratch
recreated the orignal issue, but somehow some fiddling fixed it. I wasn't sure what fix actually solved the problem so I essentially analized the
properties of every Controller and View in the storyboard until I found a discrepency between the Test (this repo), and the original project's TableView.
The issue ended up being that I accidentally changed the class of the View from UIView to the same class as my View Controller, which essentially broke
everything, and gave me an error I couldn't make much sense of until I went into the TableView's properties and found that it was linking to the View
it was contained in, and not the View Controller class I had written, essentially orphaning the object in a sort of No-Mans-Land if you will.

All and all, a (not)fun and agonizing way to spend 3 hours.
