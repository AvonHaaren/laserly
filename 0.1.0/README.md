Maybe one other thing, since I haven't documented the syntax yet, if you look in the laser-optics folder, there are subfolders for all optics that I've used and even some I haven't used yet. You can render any element using element("<name>"). Parameters of element are:

    variant [integer, default: 1]: Render a different image (see files in the subfolders of the element, e.g. lens has 1-5)
    dist [length, default: 30pt]: change the distance to the previous or next element (I currently don't remember which way it is)
    rot [deg, default 0deg]: change the rotation of the element. By default all elements should be aligned such that a laser beam goes through it centrally
    size [float, default: 1.0]: change the scale of the element
    info_pos [(top|right|bottom|left|none), default: none]: in combination with info_num, you can display a number next to the element which you can reference later
    info_num [integer, default: -1]: in combination with info_pos, you can display a number next to the element which you can reference later

Apart from that, some elements you want to render not with element(...) because they alter the beam path. These are splitters:

splitter(...)

    path1 / path2: Arrays of elements
    path3: Another array of elements. For example a beam splitter combined with a 180deg mirror would result in a laser beam exiting a third face of the beam splitter
    type: Name of an element, default "beam_splitter_cube", I also use "beam_sampler" in the thesis
    All other parameters from element(...) are also available

Another one is mirror, which turns the beam path:

    type: Name of an element, default "mirror"
    All other parameters from element(...) are also available

When you finished drawing, you can render a legend also, but I think you're seeing that in the example

If the assembly doesn't fit, I think you'll have to increase the page size. I wanted to have a way to increase the page size according to the drawing but that would have taken too much work
